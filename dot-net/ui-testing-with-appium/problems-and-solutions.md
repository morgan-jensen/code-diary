# Problems and Solutions

*Problem*: When grabbing a button with `WindowsElement button = session.FindElementByAccessibilityId()`, button.Text returns as empty, and we cannot check it. <br/>
*Solution*: The problems is caused by Appium grabbing the whole framework of the button, which does not include a 'Text' field. It does however, contain a TextBlock. The issue can be solved by calling button.FindElementByClassName("TextBlock").Text. This should return the displayed button text.
