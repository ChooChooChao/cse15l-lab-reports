# Lab Report 2

*This report will take you through the incremental programming and debugging practiced over Labs 3 and 4.*

> **BUG 1**

![Image](bug1SolutionScreenshot.PNG)

- Attached here is the [link](https://github.com/ChooChooChao/markdown-parse/commit/0f04bfd5aa2b037a428ffc4691d053719b1ef6df#diff-0c888627ccb44d27a24ecdede12f8e703504fd7bd52d792866fe2a3e33b8622a) to the failure inducing-input. 
- It is difficult to display an infinite output with a screenshot, but you may also find a part of the resulting symptoms in the commit history.
- Based off the input, we found that it was the new/extra lines at the end of the test file that caused the error. This resulted in an infinite output. Thus we changed the code so that it would account for and break the loop after the final set of brackets and parentheses. 


> **BUG 2**

![Image](bug2SolutionScreenshot.PNG)

- Attached here is the [link](https://github.com/jonathanaduong/markdown-parse/commit/1f240c328cf956799750a4deb08f3efdf1dc2533) to the failure inducing-input. 
- Below you can see the output results of the failure-inducing code

![Imaga](outputErrorForBug2.PNG)

- Though it is unlikely that there would be extra parentheses within the link, this bug considers such an input. As a result of this, we got a heap space error. We fixed this error by adding a separate check ensuring there are no brackets or parentheses within the first found opening parentheses and final closing parentheses.


> **BUG 3**

![Image](bug3SolutionScreenshot.PNG)

- Attached here is the [link](https://github.com/P2fryang/markdown-parse/commit/ff5cb42e601252cf2358e845fa64f17788dc591f) to the failure inducing-input.
- Below you can see the output resulting from this input.

![Image](outputErrorForBug3.PNG)

- This output highlights the result of having extra characters between the closing bracket and opening parentheses. In this example we see ```[]k(ing)``` in the markdown file. This would not be a valid link as the the ```](``` must be consecutive for a valid link. Thus this solution restarts the search for another closing bracket again if the index of ```(``` is not 1 more than the index of ```[```. 
