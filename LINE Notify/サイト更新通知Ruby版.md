# Rubyを使って実装
## 1,Rubyでスクリプト作成（環境変数を設定）
Nokogiri,Mechanizeなどのライブラリを使用
## 2,LINE Notifyのアカウント作成＆トークン取得
HTTPクライアントにFaradayを使用
## 3,cronジョブを設定して定期的にスクリプトを実行
## スクリプト例
```Ruby
require 'nokogiri'
require 'open-uri'
require 'faraday'

# 監視するWebサイトのURL
url = 'https://example.com/'

# Line Notify APIトークン
token = 'LINE_NOTIFY_API_TOKEN'

# スクレイピングして更新を検出
doc = Nokogiri::HTML(open(url))
if doc.css('title').text != '前回のタイトル'
  # 更新がある場合はLine通知を送信
  message = "Webサイトが更新されました: #{url}"
  conn = Faraday.new(:url => 'https://notify-api.line.me') do |faraday|
    faraday.request  :url_encoded
    faraday.adapter  Faraday.default_adapter
  end
  response = conn.post do |req|
    req.url '/api/notify'
    req.headers['Content-Type'] = 'application/x-www-form-urlencoded'
    req.headers['Authorization'] = "Bearer #{token}"
    req.body = "message=#{message}"
  end
end
```