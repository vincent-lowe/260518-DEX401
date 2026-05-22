## Text Copy Buffer

Paste or copy text from classroom experiments

--------
%dw 2.0
output application/json

var i = 42
var f = 3.1415
var b = false
var o = {k1:1,k2:2}
var a = [22,13,54,777,110,13,17]
var r = 1 to 9
var s = "some words in a row "

var aos = "if you look closely
you can find that parts of a pine
Tree are edible. But who on
earth wants to eat a pine tree" splitBy "\n"
---
/*
    Monitor Object: Allows inspection of various expressions
*/
{
    aNumber: i,
    anotherNumber: f,
    whichType: typeOf(s),
//    anObject: o,
    anArray: a,
    //anotherArray: r, // really, it's a Range
//    firstElement: a[0],
//    lastElement: a[-1], // same as a[sizeOf(a)-1]
//    middleElement: a[-3],
//    middleArray: a[2 to 5],
//    aSentence: "If you have " ++ s ++ ", you might have a sentence.", // string concatenation
//    anotherSentence: "If you have $(s), you might have a sentence.", // string interpolation
    myMessage: aos,
    sortedMessage: aos[-1 to 0],
//    orderedMessage: aos orderBy $,
    orderedNumbers: a orderBy $,
    ascendingNumbers: a orderBy (n) -> n, // same as previous line
    risingNumber: a orderBy (n) -> -1 * n,
    alsoRising: a orderBy (n) -> -n, // same as previous line
}



