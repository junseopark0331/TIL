# URL Session 예시

오늘 앨런 강의를 보고 url session을 어떻게 연결하면 좋을지에 대한 코드를 적어서 남긴다.

영화진흥위원회의 open Api서비스를 이용하는 코드입니다:)


참고용으로 100% 맞지 않을 수 있어요! 

```swift
let movieURL = "http://kobis.or.kr/kobisopenapi/webservice/rest/boxoffice/searchDailyBoxOfficeList.json?&key=⭐️본인들각자의키값입력⭐️&targetDt=20210201"


// 1. URL 구조체 만들기
let url = URL(string: movieURL)!


// 2. URLSession 만들기 (네트워킹을 하는 객체 - 브라우저 같은 역할)
let session = URLSession.shared


// 3. 세션에 (일시정지 상태로)작업 부여
let task = session.dataTask(with: url) { (data, response, error) in
    if error != nil {
        print(error!)
        return
    }
    
    guard let safeData = data else {
        return
    }
    
    // 데이터를 그냥 한번 출력해보기
    //print(String(decoding: safeData, as: UTF8.self))
    
    dump(parseJSON1(safeData)!)
    
    
}

// 4.작업시작
task.resume() 


```