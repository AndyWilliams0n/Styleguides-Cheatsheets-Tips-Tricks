# Mocha And Selenium Reference Guide

## Selenium Webdriver Commands

webdriver.By.id

    // Gets the element: #identifier
    
    <input id="identifier" />
    
    driver.findElement(webdriver.By.id('identifier'));
    
webdriver.By.className

    // Gets the element: .class
    
    <input class="class" />

    driver.findElement(webdriver.By.className('class'));

webdriver.By.name

    // Gets the element: .class
    
    <input name="name" />

    driver.findElement(webdriver.By.name('name'));

