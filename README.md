

// 타입 지정
let sname: string='ee';
sname='dd';

// 배열
let aname:string[] = ['123','eq'];


// 오브젝트
// ? 사용하면 옵셔널(특정 속성이 선택 사항인 경우)
let ob:{name?:string} = {name: 'kim'};

ob.name='lee';

// 여러가지 타입의 데이터가 들어올 수 있게 하려면 | 연산자(or 연산자)
let name: string | number = 1233;



// ! type 키워드 대신 interface 키워드로도 생성 가능
// type 키워드를 통해 사용자 지정 타입 생성 가능
// 타입명 작성할때는 대문자로 작성함
type MyTy = string | number;
let na: MyTy = 1234;

// type 에 자료형 대신 원하는 글자나 숫자를 넣으면 해당 변수에는 그 값만 넣을수 있다(literal type)
type OnlyTy = 'kim' | 123;
// let new1 : OnlyTy = 'lee'    // 타입오류
let new1 : OnlyTy = 123;



//함수
// 리턴값 타입 지정도 가능
function myFx(x:number) : number{
    return x*2;
}
// 리턴 타입으로 void 설정 가능(return이 있는지 없는지 체크할 수 있는 타입)
myFx(123);


//지금 변수의 타입이 확실하지 않으면 마음대로 연산하지 않음(오류띄움)
// function myFx2(y:number | string) {
//     return y+2;
// }

// 항상 타입이 무엇인지 알려줘야함
function myFx2(y:number | string) {
    if(typeof y ==='number')
    return y+2;
}


//array에 순서를 포함해서 어떤 자료들이 들어와야 한다 이런식 할때?
type Members = [number, boolean];   // tuple 타입   [] 안에 들어올 자료의 타입을 차례로 적어준다
let john: Members = [123, true];    // 반드시 이 순서로 자료형이 들어와야함



//object 자료형
type Groups = {
    // name: string;    // 특정 속성에 대한 자료형 지정
    [key:string] : string | number;  // 글자로 된 모든 오브젝트 속성의 타입은 string 이여야 한다는 뜻
    // 오브젝트 안에 어떤 속성이 들어갈지 아직 모르는 경우 그냥 싸잡아서 타입 지정(index signature)
}

let edward : Groups = {
    name : ' ki', 
    gender:'male',
    age: 24,
};


//클래스도 타입 지정 가능
class User {
    name;   //! 다만, 클래스형에서는 미리 변수를 만들어둬야 함
    constructor(name: string) {
        this.name= name;
    }
}





export {}
