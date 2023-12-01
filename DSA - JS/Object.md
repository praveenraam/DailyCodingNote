Topic to know before [[Array Introduction]]
Next Topic : [[Set]]

- An object is an unordered collection of key-value pairs. The key must
- string or symbol data type where as the value can be of any data type
- To retrieve a value, you can use the the corresponding key.
- This can using the dot notation or bracket notation
- An object is not an iterable. You cannot use it with a for of loop

```js
const obj = {
        Person1 :{
            Name:'Premnath',
            Age : 'Unknown'
        },
        Person2 : {
            Name: 'Praveen',
            Age : '19'
        },
        HelloWorld : function(){
            console.log('Hello World!')
        }
    }

    obj.Person1.Hobbies = 'Sports'

    console.log(obj.Person1.Hobbies)
    console.log(obj.Person1.Age)
    console.log(obj['Person2']['Name'])

    delete obj.Person2

    console.log(obj)

    obj.HelloWorld()
```

Object can be noted using the dot notation or bracket notation


#### Object - Big-O time complexity
- Insert – O(1)
- Remove - O(1)
- Access – O(1)
- Search - O (n)
- Object.keys() - O(n)
- Object.values() – O(n)
- Object.entries() - O(n)
