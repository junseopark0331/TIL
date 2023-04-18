# Head 방식으로 연결하기



```swift
extension IdSignupViewController{
    
    
    func requestPOST() {
        
        guard let id = idTextField.text else { return }
        
        print(id)
        
        // [URL 지정 및 파라미터 값 지정 실시]
        var urlComponents = URLComponents(string: "https://api.glog.kro.kr/auth/valid-id?=userId=\(id)")
        
        let userIdQuery = URLQueryItem(name: "userId", value: id)

        urlComponents?.queryItems?.append(userIdQuery)
        
        
        // [http 통신 타입 및 헤더 지정 실시]
        var requestURL = URLRequest(url: (urlComponents?.url)!)
        requestURL.httpMethod = "HEAD"
        
//        requestURL.addValue("application/json", forHTTPHeaderField: "userId")
//        requestURL.addValue(id, forHTTPHeaderField: "userId")
        
        // [http 요쳥을 위한 URLSessionDataTask 생성]
        print("")
        print("====================================")
        print("[requestPOST : http post 요청 실시]")
        print("url : ", requestURL)
        print("====================================")
        print("")
        
        let dataTask = URLSession.shared.dataTask(with: requestURL) { (data, response, error) in
            // [error가 존재하면 종료]
            guard error == nil else {
                print("")
                print("====================================")
                print("[requestPOST : http post 요청 실패]")
                print("fail : ", error?.localizedDescription ?? "")
                print("====================================")
                print("")
                return
            }
            
            // [status 코드 체크 실시]
            let successsRange = 200..<300
            
            guard let statusCode = (response as? HTTPURLResponse)?.statusCode, successsRange.contains(statusCode)
            else {
                print("")
                print("====================================")
                print("[requestPOST : http post 요청 에러]")
                print("error : ", (response as? HTTPURLResponse)?.statusCode ?? 0)
                print("msg : ", (response as? HTTPURLResponse)?.description ?? "")
                print("====================================")
                print("")
                return
            }
            
            // [response header cookies 데이터 확인]
            let cookies = HTTPCookie.cookies(withResponseHeaderFields: (response as? HTTPURLResponse)?.allHeaderFields as! [String : String], for: (urlComponents?.url)!)
            print("")
            print("====================================")
            print("[requestPOST : http post 요청 성공]")
            print("response header cookies : ", cookies)
            print("====================================")
            print("")
            
            // [response 데이터 획득, utf8인코딩을 통해 string형태로 변환]
            let resultCode = (response as? HTTPURLResponse)?.statusCode ?? 0
            let resultLen = data! // 데이터 길이
            let resultString = String(data: resultLen, encoding: .utf8) ?? "" // 응답 메시지
            print("")
            print("====================================")
            print("[requestPOST : http post 요청 성공]")
            print("resultCode : ", resultCode)
            print("resultLen : ", resultLen)
            print("resultString : ", resultString)
            print("====================================")
            print("")
        }
        // network 통신 실행
        dataTask.resume()
    }
    
    func idConditionFailAlert(){
        let alert = UIAlertController(
            title: "에러",
            message: "아이디가 조건에 맞지 않습니다",
            preferredStyle: .alert)
        
        let defaultAction = UIAlertAction(title: "확인", style: .default, handler: nil)
        
        alert.addAction(defaultAction)
        
        present(alert, animated: false, completion: nil)
    }
    
    func sameIdAlert(){
        let alert = UIAlertController(
            title: "아이디 중복",
            message: "아이디가 중복됩니다",
            preferredStyle: .alert)
        
        let defaultAction = UIAlertAction(title: "확인", style: .default, handler: nil)
        
        alert.addAction(defaultAction)
        
        present(alert, animated: false, completion: nil)
    }
    
}
```

처음으로 url session을 이용하여 연결해보았다.

배껴서 쓰기보단 필요하신것만 복사해서 쓰는걸 추천해드려요! 

더 나은 코드로 TIL 적어보겠습니다! 