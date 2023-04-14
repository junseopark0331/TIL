어젯밤, 퍼블리슁을 하면서 

```swift
class ViewController: UIViewController {
    
    var menuName: [String] = ["치킨팝","꽃게랑","도리토스","콘칩","O"]
    
    lazy var collectionView: UICollectionView = {
        let view = UICollectionView(frame: .zero, collectionViewLayout: flowLayout)
        view.backgroundColor = .white
        
        return view
    }()
    
    private let flowLayout = UICollectionViewFlowLayout().then{
        $0.itemSize = CGSize(width: 226, height: 355)
        $0.scrollDirection = .horizontal
        $0.minimumLineSpacing = 40
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        view.addSubview(collectionView)
        self.collectionView.delegate = self
        self.collectionView.dataSource = self
        
        self.collectionView.register(MyCell.self, forCellWithReuseIdentifier: MyCell.id)
        self.collectionView.collectionViewLayout = flowLayout
    
    }
    
    
    func setLayout(){
        self.collectionView.snp.makeConstraints {
            $0.top.equalToSuperview().offset(353)
            $0.bottom.equalToSuperview().inset(285)
            $0.leading.equalToSuperview().offset(133)
            $0.trailing.equalToSuperview().inset(133)
        }
    }
    
}
```

위와 같은 코드가 왜 실행되지 않아 레이아웃부분을 계속 살펴보았다.

물론 레이아웃 부분에도 약간의 문제가 있었지만 위의 코드가 실행되지 않았었던 이유는
 레이아웃을 설정해주는 함수인 setLayout()을 viewDidLoad에서 실행시키지 않았었기 때문이다.. ㅠ


 ```swift
 override func viewDidLoad() {
        super.viewDidLoad()
        
        view.addSubview(collectionView)
        self.collectionView.delegate = self
        self.collectionView.dataSource = self
        
        self.collectionView.register(MyCell.self, forCellWithReuseIdentifier: MyCell.id)
        self.collectionView.collectionViewLayout = flowLayout
        
        setLayout()
    }
````
이렇게 viewDidLoad 안에 레이아웃함수를 실행시켜주면 화면이 내가 생각했던대로 잘 나오는걸 볼 수 있다.

**결론 : 화면에 아무것도 보이지 않을때에는 레이아웃 함수를 확인해보자!**