# Project 6

Project 6 was more work on classes, and how to use them with each other with the <i>extend</i> keyword:
```ruby
const data = [ [3, 4], [5, 5], [3, 4, 5], [10], [] ];

function process(){
    for(d of data){
        let shape = null;
        switch(d.length){ 
            case 2:
                shape = new Rectangle(...d);
                let square = shape.length == shape.width ? "Square" : "Rectangle";
                console.log(`${square} with sides ${d.toString()} has perimeter of ${shape.perimeter()} and area of ${shape.area()}`);
                break;
            case 3:
                shape = new Triangle(...d);
                console.log(`Triangle with sides ${d.toString()} has perimeter of ${shape.perimeter()} and area of ${shape.area()}`);
                break;
            default:
                console.log(`Shape with ${d.length} side unsupported`);
                break;
        }
    }
}

process();
```

Each class was pretty simple, only including a function or two:
```ruby
class Shape{
    constructor(sides = []){
        this.sides = sides;
    }

    perimeter(){
        return this.sides.length > 1 ? this.sides.reduce((total, num) => {
            return total + num;
        }) : 0;
    };
}


class Rectangle extends Shape{
    constructor(length = 0, width = 0){
        super([length, width, length, width]);
        this.length = length;
        this.width = width;
    }

    area(){
        return this.length * this.width;
    }
}
```
<a href="https://joeybez.github.io/joeybezner.github.io/">Back to Home</a>
