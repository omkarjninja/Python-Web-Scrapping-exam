!pip install twisted==21.7.0
<br>
pip install scrapy<br>
import scrapy<br>
<br>
class MySpider (scrapy. Spider):<br>
    name = "myspider"<br>
    start_urls = ["https://presidencyuniversity.in",]<br>
    def parse(self, response):<br>
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
