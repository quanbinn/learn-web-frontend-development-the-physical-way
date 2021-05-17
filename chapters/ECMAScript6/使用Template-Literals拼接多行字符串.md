# 使用Template Literals拼接多行字符串

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20student%20%3D%20%7B%0A%20%20name%3A%20'Richard%20Kalehoff',%0A%20%20guardian%3A%20'Mr.%20Kalehoff'%0A%7D%3B%0A%0Aconst%20teacher%20%3D%20%7B%0A%20%20name%3A%20'Mrs.%20Wilson',%0A%20%20room%3A%20'N231'%0A%7D%0A%0Alet%20note%20%3D%20teacher.name%20%2B%20',%5Cn%5Cn'%20%2B%0A%20%20'Please%20excuse%20'%20%2B%20student.name%20%2B%20'.%5Cn'%20%2B%0A%20%20'He%20is%20recovering%20from%20the%20flu.%5Cn%5Cn'%20%2B%0A%20%20'Thank%20you,%5Cn'%20%2B%0A%20%20student.guardian%3B%0A%0A//%20let%20note%20%3D%20%60%24%7Bteacher.name%7D,%0A%0A//%20%20%20Please%20excuse%20%24%7Bstudent.name%7D.%0A//%20%20%20He%20is%20recovering%20from%20the%20flu.%0A%20%20%0A//%20%20%20Thank%20you,%0A//%20%20%20%24%7Bstudent.guardian%7D%60%3B%0A%20%20%0Aconsole.log%28note%29%3B&cumulative=false&curInstr=4&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const student = {
  name: 'Richard Kalehoff',
  guardian: 'Mr. Kalehoff'
};

const teacher = {
  name: 'Mrs. Wilson',
  room: 'N231'
}

let note = teacher.name + ',\n\n' +
  'Please excuse ' + student.name + '.\n' +
  'He is recovering from the flu.\n\n' +
  'Thank you,\n' +
  student.guardian;

// let note = `${teacher.name},

//   Please excuse ${student.name}.
//   He is recovering from the flu.
  
//   Thank you,
//   ${student.guardian}`;
  
console.log(note);
```

单击右方的[在线代码段Url网址](http://www.pythontutor.com/live.html#code=const%20cheetah%20%3D%20%7B%0A%20%20%20%20name%3A%20'Cheetah',%0A%20%20%20%20scientificName%3A%20'Acinonyx%20jubatus',%0A%20%20%20%20lifespan%3A%20'10-12%20years',%0A%20%20%20%20speed%3A%20'68-75%20mph',%0A%20%20%20%20diet%3A%20'carnivore',%0A%20%20%20%20summary%3A%20'Fastest%20mammal%20on%20land,%20the%20cheetah%20can%20reach%20speeds%20of%2060%20or%20perhaps%20even%2070%20miles%20%2897%20or%20113%20kilometers%29%20an%20hour%20over%20short%20distances.%20It%20usually%20chases%20its%20prey%20at%20only%20about%20half%20that%20speed,%20however.%20After%20a%20chase,%20a%20cheetah%20needs%20half%20an%20hour%20to%20catch%20its%20breath%20before%20it%20can%20eat.',%0A%20%20%20%20fact%3A%20'Cheetahs%20have%20%E2%80%9Ctear%20marks%E2%80%9D%20that%20run%20from%20the%20inside%20corners%20of%20their%20eyes%20down%20to%20the%20outside%20edges%20of%20their%20mouth.'%0A%7D%3B%0A%0A//%20creates%20an%20animal%20trading%20card%0Afunction%20createAnimalTradingCardHTML%28animal%29%20%7B%0A%20%20%20%20//%20const%20cardHTML%20%3D%20'%3Cdiv%20class%3D%22card%22%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20'%3Ch3%20class%3D%22name%22%3E'%20%2B%20animal.name%20%2B%20'%3C/h3%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20'%3Cimg%20src%3D%22'%20%2B%20animal.name%20%2B%20'.jpg%22%20alt%3D%22'%20%2B%20animal.name%20%2B'%22%20class%3D%22picture%22%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20'%3Cdiv%20class%3D%22description%22%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20'%3Cp%20class%3D%22fact%22%3E'%20%2B%20animal.fact%20%2B%20'%3C/p%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20'%3Cul%20class%3D%22details%22%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20%20%20%20%20'%3Cli%3E%3Cspan%20class%3D%22bold%22%3EScientific%20Name%3C/span%3E%3A%20'%20%2B%20animal.scientificName%20%2B%20'%3C/li%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20%20%20%20%20'%3Cli%3E%3Cspan%20class%3D%22bold%22%3EAverage%20Lifespan%3C/span%3E%3A%20'%20%2B%20animal.lifespan%20%2B%20'%3C/li%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20%20%20%20%20'%3Cli%3E%3Cspan%20class%3D%22bold%22%3EAverage%20Speed%3C/span%3E%3A%20'%20%2B%20animal.speed%20%2B%20'%3C/li%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20%20%20%20%20'%3Cli%3E%3Cspan%20class%3D%22bold%22%3EDiet%3C/span%3E%3A%20'%20%2B%20animal.diet%20%2B%20'%3C/li%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20'%3C/ul%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20%20%20%20%20'%3Cp%20class%3D%22brief%22%3E'%20%2B%20animal.summary%20%2B%20'%3C/p%3E'%20%2B%0A%20%20%20%20//%20%20%20%20%20'%3C/div%3E'%20%2B%0A%20%20%20%20//%20'%3C/div%3E'%3B%0A%20%20%20%20%0A%20%20%20%20const%20cardHTML%20%3D%20%60%3Cdiv%20class%3D%22card%22%3E%0A%20%20%20%20%20%20%20%20%3Ch3%20class%3D%22name%22%3E%24%7Banimal.name%7D%3C/h3%3E%0A%20%20%20%20%20%20%20%20%3Cimg%20src%3D%22%24%7Banimal.name%7D.jpg%22%20alt%3D%22%24%7Banimal.name%7D%22%20class%3D%22picture%22%3E%0A%20%20%20%20%20%20%20%20%3Cdiv%20class%3D%22description%22%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cp%20class%3D%22fact%22%3E%24%7Banimal.fact%7D%3C/p%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cul%20class%3D%22details%22%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%3Cli%3E%3Cspan%20class%3D%22bold%22%3EScientific%20Name%3C/span%3E%3A%20%24%7Banimal.scientificName%7D%3C/li%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%3Cli%3E%3Cspan%20class%3D%22bold%22%3EAverage%20Lifespan%3C/span%3E%3A%20%24%7Banimal.lifespan%7D%3C/li%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%3Cli%3E%3Cspan%20class%3D%22bold%22%3EAverage%20Speed%3C/span%3E%3A%20'%24%7Banimal.speed%7D%3C/li%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%3Cli%3E%3Cspan%20class%3D%22bold%22%3EDiet%3C/span%3E%3A%20%24%7Banimal.diet%7D%3C/li%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3C/ul%3E%0A%20%20%20%20%20%20%20%20%20%20%20%20%3Cp%20class%3D%22brief%22%3E%24%7Banimal.summary%7D%3C/p%3E%0A%20%20%20%20%20%20%20%20%3C/div%3E%0A%20%20%20%20%3C/div%3E%60%3B%20%20%20%20%0A%0A%20%20%20%20return%20cardHTML%3B%0A%7D%0A%0Aconsole.log%28createAnimalTradingCardHTML%28cheetah%29%29%3B&cumulative=false&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-live.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false)，浏览器里会打开一个新的页面，里面有下面的代码段。

```javascript
const cheetah = {
    name: 'Cheetah',
    scientificName: 'Acinonyx jubatus',
    lifespan: '10-12 years',
    speed: '68-75 mph',
    diet: 'carnivore',
    summary: 'Fastest mammal on land, the cheetah can reach speeds of 60 or perhaps even 70 miles (97 or 113 kilometers) an hour over short distances. It usually chases its prey at only about half that speed, however. After a chase, a cheetah needs half an hour to catch its breath before it can eat.',
    fact: 'Cheetahs have “tear marks” that run from the inside corners of their eyes down to the outside edges of their mouth.'
};

// creates an animal trading card
function createAnimalTradingCardHTML(animal) {
    // const cardHTML = '<div class="card">' +
    //     '<h3 class="name">' + animal.name + '</h3>' +
    //     '<img src="' + animal.name + '.jpg" alt="' + animal.name +'" class="picture">' +
    //     '<div class="description">' +
    //         '<p class="fact">' + animal.fact + '</p>' +
    //         '<ul class="details">' +
    //             '<li><span class="bold">Scientific Name</span>: ' + animal.scientificName + '</li>' +
    //             '<li><span class="bold">Average Lifespan</span>: ' + animal.lifespan + '</li>' +
    //             '<li><span class="bold">Average Speed</span>: ' + animal.speed + '</li>' +
    //             '<li><span class="bold">Diet</span>: ' + animal.diet + '</li>' +
    //         '</ul>' +
    //         '<p class="brief">' + animal.summary + '</p>' +
    //     '</div>' +
    // '</div>';
    
    const cardHTML = `<div class="card">
        <h3 class="name">${animal.name}</h3>
        <img src="${animal.name}.jpg" alt="${animal.name}" class="picture">
        <div class="description">
            <p class="fact">${animal.fact}</p>
            <ul class="details">
                <li><span class="bold">Scientific Name</span>: ${animal.scientificName}</li>
                <li><span class="bold">Average Lifespan</span>: ${animal.lifespan}</li>
                <li><span class="bold">Average Speed</span>: '${animal.speed}</li>
                <li><span class="bold">Diet</span>: ${animal.diet}</li>
            </ul>
            <p class="brief">${animal.summary}</p>
        </div>
    </div>`;    

    return cardHTML;
}

console.log(createAnimalTradingCardHTML(cheetah));
```

## 参考文献及资料

1. [Template literals (**Template strings**)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
2. [**ES6** from Udacity.com](https://classroom.udacity.com/courses/ud356)

