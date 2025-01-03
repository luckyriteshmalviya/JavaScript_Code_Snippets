# JavaScript_Code_Snippets
JavaScript Code Based question for core concepts


**1.**  
var a = 3;  
var b = {  
  a: 9,  
  b: ++a  
};  
console.log(a + b.a + ++b.b);  

<details>  
<summary>Answer</summary>
18
</details>

========================================================================

**2.**    
var a = 3;  
var b = {  
  a: 9,  
  b: a++  
};  
console.log(a + b.a + ++b.b);  

<details>  
<summary>Answer</summary>
17
</details>

========================================================================

**3.**   
console.log([1] + [])
<details>  
<summary>Answer</summary>
1
</details>

========================================================================

**4.**   
console.log([1] + [1])
<details>  
<summary>Answer</summary>
11
</details>

========================================================================

**5.**  
var a = (2, 3, 5) 
console.log(a)
<details>  
<summary>Answer</summary>
5
</details>

========================================================================

**6.**  
typeof(NaN)
<details>  
<summary>Answer</summary>
"number"
</details>

========================================================================

**7.**   
Math.max([ 2,3,45])
<details>  
<summary>Answer</summary>
NaN
</details>

========================================================================

**8.**   
function Operations(input) {     
return {  
sum: (...args) =>arguments[0] + input }  
}  
  
const ops = Operations(0.1)   
  
console.log(ops.sum(1, 2,3))  
<details>    
<summary>Answer</summary>
0.2  
</details>

========================================================================

**9.**   
function a(){  
    this.setTimeout(()=>console.log('test a'))  
}  
  
const b = ()=>{  
    this.setTimeout(()=>console.log('test b'))  
}  
a()  
b()  
<details>  
<summary>Answer</summary>
test a  
test b
</details>

========================================================================

**10.**   
function createCounter(){    
   let count = 0;  
   function increase(){  
   count++;    
}  
let message = `Count is ${count}`;  
function log(){  
console.log(message);  
}  
return [increase, log];  
}    
    
const [increase, log]= createCounter();  
increase();  
increase();  
increase();  
log();  
<details>  
<summary>Answer</summary>
Count is 0       
=>  Increase() is called three times successively, incrementing the count variable each time.  
After the three calls to increase(), count becomes 3.  
However, the log() function within createCounter captures the message variable at the time of its creation, which happens before any calls to increase(). Therefore, the message   variable inside log() still holds the initial value of Count is 0.  
</details>

========================================================================

**11.**   

(function (a) {  
return (function (b){  
console.log(a);  
})(1)  
})(0)   
  
<details>    
<summary>Answer</summary>
0  
</details>

========================================================================

**12**   

var number = 10;  
var display = function(){  
    console.log(number);  
    var number = 20;  
}  
display()   
    
<details>      
<summary>Answer</summary>   
undefined   
</details>  

========================================================================

**13.**    
  
const getUser = async () => {  
  return new Promise((resolve) => {  
    setTimeout(() => {  
      resolve({ id: 1, username: "john_doe" });  
    }, 1000);  
  });  
};  
  
const getPosts = async () => {  
  return new Promise((resolve) => {  
    setTimeout(() => {  
      resolve(["post1", "post2", "post3"]);  
    }, 6500);  
  
  setTimeout(() => {  
      resolve({ message: "API Timeout" });  
    }, 2000);  
  });  
};  
  
const displayUserInfo = async () => {   
  const user = await getUser();  
  const posts = await getPosts();  
  return { user, posts };  
};  
  
displayUserInfo().then((result) => console.log(result));  
  
<details>      
<summary>Answer</summary>   
{    
    "user": {  
        "id": 1,  
        "username": "john_doe"  
    },  
    "posts": {  
        "message": "API Timeout"  
    }  
}  
</details>  


========================================================================

**14.** 

var obj1 = {  
    address : "Mumbai,India",  
    getAddress: function(){  
    console.log(this.address);   
  }  
}  
     
var getAddress = obj1.getAddress;  
var obj2 = {name:"akshay"};  
obj2.getAddress();  

<details>      
<summary>Answer</summary>   
obj2.getAddress is not a function    
</details>  



========================================================================

**15.** 

const arr = [1,2,3]  
const str = "1,2,3"  
  
console.log(arr == str)

<details>      
<summary>Answer</summary>   
true  
</details>  
