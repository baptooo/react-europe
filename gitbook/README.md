## Mobx 10:00 AM

store restore snapshots
- cache
- offline

+ runtime type checking
+ replayable actions

## Composition 10.30 AM

chain in lodash, limitation : not extendable

pipe versus chaining
- easier syntaxe

pipe
- function composition

```js
pipe(a, b, c, d)
```

order from d to a and share result between each function until final result

### In React ?

Enhance components with functions

```js
import { compose } from 'ramda';
```

declarative composition for preventing function nesting

>**Polished** : css in js tool with composition

Compose styles to components

**Example**
```js
const tmpColor = lighten(0.3, '#F50');
```

Lighten can be composed with any color modification function

Requirements:
- input/output css values in functions
- every function return a function with color as an argument

**currying** notion : transform each arguments to a function

Native support in some languages
- ReasonML
- ELM

>lodash map : Revert arguments for composition
```js
map((name => name), names)
```

**Loading indicator example**

### Automatically condition Component with a loading state from props

```js
const withLoading = Component => ({ loading }) => (
  loading ? <div>loading</div> : <Component />
);
```

### With text

```js
const withLoading = text => Component => ({ loading }) => (
  loading ? <div>{text}</div> : <Component />
);

withLoading('Loading')(<section />);
```

**Animation example**

In this example 3D rendering is used and the animation of the y axis is extracted in a HOC

Benefits :
- testability
- isolation
- reusability

## The making of Twitter Lite 11:00 AM

Issue : slow internet dominates
- 47% 2G connection
- 21% 4G
- other 3G

The need of a very performant PWA

**Performance optimization**

Painting cycle :
- Splashscreen
- Header
- Content (First meaningful Paint)
- Interactive

### Working ideas

- Involving designers with shared language for better interface communication
- Full flexbox layout

## Lightning talks 12:00 AM

### React key prop

- known performance issue
- Performance benchmark with 5k iterations list with component render of 10ms

Functional component
Key ~60.1ms
NoKey ~60.3ms

PureComponent
Key ~1.3ms
NoKey ~19.9ms

>Always set keys !!!

### Async Import chunks

- stage-3 spec

```js
const React = await import('react');
```

Can be used to async components

Suggested strategy :
- split app and vendor code
- split at route level (async)
- split at component level (async)

## Lunch 12:30 AM

![](https://media3.giphy.com/media/GnCc88zZhSVUc/giphy.gif?response_id=591eca088ce1123c7f7f2a76)

## React VR 2:00 PM

>VR is hard

Features
- 2D basics
- 3D Concepts
- Multimedia

Goal : easy access to VR with React

Used on prod for Facebook VR videos / photospheres

### Dev tools

chrome dev tools...

### Techniqual stack

State :
- Redux

Testing :
- flow + jest

### Architecture

**React VR Core**
Core renderer using system APIS

**React VR JS Runtime**
HMI management with Three.js and browser apis

Layout with [facebook/yoga](https://facebook.github.io/yoga/)


