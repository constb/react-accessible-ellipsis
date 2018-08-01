# react-accessible-ellipsis
Truncate multiline with an ellipsis... without causing accessibility problems

## Why?

For visual reasons it can be informative to show that text has been truncated with an ellipsis character "...", such as

    It was the best of times, it was the worst of...

However browser support for `text-overflow:ellipsis` is poor, especially on multiline text.

There are a variety of JavaScript-based solutions that aim to solve this but they either have poor accessibility or poor browser support, or they require `text-align: justify`.

* **Better accessibility** CSS `text-overflow:ellipsis` does not affect whether screenreaders have their text truncated and neither should a JavaScript approach. Most alternatives truncate the sentence which may make for nonsensical text being read to screen reader users. The ellipsis is visual decoration and that's it.
* **Better browser support** this is a JavaScript solution that works everywhere React does.
* **Arbitrary alignment** this doesn't require `text-align: justify` and works with any text or font (variable width or fixed etc.).

Please note that it only supports plaintext though, not HTML (the `children` node should just be plaintext).

## Install

    npm install react-accessible-ellipsis

    yarn add react-accessible-ellipsis
    
## Usage

Put `<Ellipsis>` tags around your text, and ensure that it's only used within a component with a set height

    import Ellipsis from 'react-accessible-ellipsis';

    export default () => (
      <Ellipsis style={{height: '2em' }}> any text you want lorem ipsum etc. </Ellipsis>
    )

or,

    export default () => (
      <Ellipsis className="some-class-with-height"> any text you want lorem ipsum etc. </Ellipsis>
    )