# DIBI BNPB Website Scrapping Using Selenium and Beautiful Soup
This project will discuss web scrapping techniques using Selenium for data retrieval that requires interaction with the website. Specifically, this project will take data from the DIBI BNPB website which has a dropdown menu.

## Selenium
Selenium is a powerful tool for automating web browsers. It works by controlling the browser through a driver, sending commands to the browser and retrieving the results. Selenium uses WebDriver to interact with web browsers. Selenium will give us access to interact with web elements using various locators such as ID, class name, and others. Selenium can also refresh web pages, navigate, click buttons, select dropdown menus, and various other actions.

## Beautiful Soup
Beautiful Soup is a Python module used for parsing HTML and XML. This library allows you to navigate, search, and modify HTML/XML documents easily. Using this module, data from the web can be retrieved after determining certain tags that contain the data sought.

## Data Informasi Bencana Indonesia BNPB
BNPB is the abbreviation of Badan Nasional Penanggulangan Bencana. This is an Indonesian government agency responsible for disaster management throughout Indonesia. As the agency with authority for disaster management, BNPB presents Indonesian Disaster Information Data (DIBI) which contains statistical data and profiles of disasters in Indonesia from 1950 to 2024. This data can be accessed on the website https://dibi.bnpb.go.id/.

![DIBI website.png](https://github.com/annisatierra/Web-Scrapping/blob/main/DIBI%20website.png)

The appearance of this website is as follows. The website uses dropdown menus to select the year, type of disaster, and province. Once selected, the website will display data regarding the number of disasters, the number of victims (dead, missing, injured, suffering, displaced), and the number of buildings affected (houses, educational facilities, health facilities, worship facilities, public facilities).

## Web Scrapping DIBI Website
![Watch the video](https://github.com/annisatierra/Web-Scrapping/blob/main/GIF.gif)


