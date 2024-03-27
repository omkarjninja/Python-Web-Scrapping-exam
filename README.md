!pip install twisted==21.7.0
pip install scrapy
import scrapy

class MySpider (scrapy. Spider):
    name = "myspider"
    start_urls = ["https://presidencyuniversity.in",]
    def parse(self, response):
        title = response.css('title::text').get()
        paragraph = response.css('p::text').get()
        print("Title: %s" %title)
        print("Paragraph: %s" %paragraph)
        yield {
            'title' : Title,
            'paragraph': Paragraph
            }
from scrapy.crawler import CrawlerProcess

process = CrawlerProcess (settings = {
'FEED_FORMAT': 'json',
'FEED_URI' : 'output.json'
})

process.crawl (MySpider)

process.start()
