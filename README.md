# 유튜브 동영상 댓글 추출기
유튜브 동영상 댓글 추출기는 유튜브 동영상에 남겨진 댓글을 크롤링 해주는 프로그램이다.
## Features
- 영상 제목 또는 URL 입력
- 댓글 목록 확인
## Requirements
- Python 
- BeautifulSoup
- Selenium
- pandadas
- requests
## Functions
### get_urls_from_youtube_with_keyword(keyword)
- 원하는 키워드에 대한 유튜브 영상 제목과 URL을 Crawling 하는 함수
- 여러 영상의 제목을 담은 titles와 URL을 담은 urls를 return 함
### crawl_youtube_page_html_sources(urls)
- 여러 영상에 대한 url을 담은 urls 리스트를 인자로 받음
- 각 URL 마다 Selenium으로 접근하여 댓글이 모두 로딩 될 수 있도록 스크롤을 시행하고
- 스크롤이 끝나면 HTML 코드를 Crawl한 후
- 리스트에 담아 return 함
### get_user_IDs_and_comments(html_sources)
- HTML 소스코드가 담겨있는 리스트를 인자로 받음
- 각 페이지 소스코드에서 댓글 데이터 부분만 추출하고
- 리뷰 데이터에서 ID값과 댓글 부분을 추출한 후
- 페이지 별로 DataFrame형식으로 만든 뒤
- 모든 페이지에 대한 DataFrame을 리스트에 담아 return 함
### convert_csv_from_dataframe(titles, my_dataframe)
- 영상의 제목들이 담긴 titles와 ID, comment 정보가 담긴 dataframe들이 들어있는 my_dataframe 리스트를 인자로 받음
- titles의 제목들에서 특수문자를 제거한 제목을 csv 파일의 이름으로 사용하여
- 각각의 dataframe을 to_csv 를 활용해 csv파일로 저장함
## License
[MIT](https://choosealicense.com/licenses/mit/) © [송은정](http://songej.com/)
