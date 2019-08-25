# Bottom input field

- [Use case](#use-case)
- [Issues](#issues)
- [Solutions](solutions)


## Use case

Very common pattern seen in the chatting app.

## Issues

Bottom input field works fine when using build-in keyboard,   
but it will be coverd partly by third party keyboard, which is  
prevalent in Android user.  

## Solutions

1. Force the bottom field to scoll into the view,  
   by selecting the target element,  
   and call it's scrollIntoView() function

    > The Element interface's `scrollIntoView()` method scrolls the element's parent container  
    > such that the element on which `scrollIntoView()` is called is visible to the user  
    > -- MDN

2. Also the idea as same as above, but `window.scrollTo()` instead.
   
    > `Window.scrollTo()` scrolls to a particular set of coordinates in the document.
    > window.scrollTo(x-coord, y-coord)
    > window.scrollTo(options)
    > --- MDN

   x and y are easy to grasp

   let's talk about options, and a example is worth million words:

        window.scrollTo({
            top: 100,
            left: 100,
            behavior: 'smooth'
        });
        
    It's a `ScrollToOptions` and quote from MDN:

    > The `ScrollToOptions` dictionary of the CSSOM View spec contains properties specifying  
    > where an element should be scrolled to, and whether the scrolling should be smooth.


For more on scroll:

[scrollIntoView()](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)  
[scrollTo()](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo)

Screenshot:

![Just a screenshot](/screenshot/screenshot.png)