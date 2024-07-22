# DIBI BNPB Website Scrapping Using Selenium
Projek ini akan membahas teknik web scrapping menggunakan Selenium untuk pengambilan data yang memerlukan interaksi dengan website. Secara khusus, proyek ini akan mengambil data dari website DIBI BNPB yang memiliki dropdown menu.
---

## Selenium

## Data Informasi Bencana Indonesia BNPB
BNPB adalah singkatan dari Badan Nasional Penanggulangan Bencana. Ini adalah sebuah badan pemerintah Indonesia yang bertanggung jawab atas penanggulangan bencana di seluruh wilayah Indonesia. Sebagai badan yang berwenang dalam penanggulangan bencana, BNPB menyajikan Data Informasi Bencana Indonesia (DIBI) yang berisikan data statistik dan profil bencana di Indonesia dari tahun 1950 hingga 2024. Data ini dapat diakses pada website https://dibi.bnpb.go.id/.

Tampilan website ini adalah sebagai berikut. Website menggunakan menu dropdown untuk memilih tahun, jenis bencana, dan provinsi. Setelah dipilih, website akan memunculkan data mengenai jumlah bencana, jumlah korban (meninggal, hilang, terluka, menderita, mengungsi), dan jumlah bangunan terdampak (rumah, fasilitas pendidikan, fasulitas kesehatan, fasilitas peribadatan, fasilitas umum)

Selenium is a powerful tool for automating web browsers. It works by controlling a browser through a driver, sending commands to the browser and retrieving results. Here’s a breakdown of how Selenium works:

### Components of Selenium

1. **Selenium WebDriver**: This is the core component that allows Selenium to interact with web browsers. Each browser (e.g., Chrome, Firefox, Safari) has its own driver that understands the browser's functionality and can control it.

2. **Selenium Server**: This is used for remote execution of WebDriver scripts. It acts as a middleman between the WebDriver client and the browser. This is particularly useful for running tests on a grid of multiple machines and browsers.

3. **Browser Drivers**: These are browser-specific drivers that translate WebDriver commands into actions on the browser. Examples include ChromeDriver, GeckoDriver (for Firefox), and EdgeDriver.

### How Selenium Works

1. **Setting Up the Environment**:
    - **Install Selenium library**: You install the Selenium library for the programming language you are using (e.g., Python).
    - **Download the browser driver**: You download the appropriate driver for the browser you intend to automate (e.g., ChromeDriver for Chrome).

2. **Creating a WebDriver Instance**:
    - You create an instance of the WebDriver for the browser you want to control. This WebDriver instance will start the browser and allow you to interact with it.
    - Example in Python:
      ```python
      from selenium import webdriver
      from selenium.webdriver.chrome.service import Service
      from webdriver_manager.chrome import ChromeDriverManager

      driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()))
      ```

3. **Navigating to Web Pages**:
    - You use the WebDriver instance to open a web page by providing the URL.
    - Example:
      ```python
      driver.get("https://example.com")
      ```

4. **Interacting with Web Elements**:
    - Selenium allows you to locate web elements (like buttons, links, text fields) using various locators such as ID, name, class name, tag name, CSS selector, and XPath.
    - You can perform actions on these elements, such as clicking, sending text, and retrieving text.
    - Example:
      ```python
      search_box = driver.find_element(By.NAME, "q")
      search_box.send_keys("Selenium")
      search_box.submit()
      ```

5. **Handling Browser Actions**:
    - Selenium can perform various browser actions, such as navigating back and forth, refreshing the page, handling alerts, switching between windows or tabs, and taking screenshots.
    - Example:
      ```python
      driver.back()  # Navigate back
      driver.refresh()  # Refresh the page
      ```

6. **Waiting for Elements**:
    - Selenium provides mechanisms to wait for elements to be available before interacting with them. This can be done using implicit or explicit waits.
    - Example of explicit wait:
      ```python
      from selenium.webdriver.common.by import By
      from selenium.webdriver.support.ui import WebDriverWait
      from selenium.webdriver.support import expected_conditions as EC

      wait = WebDriverWait(driver, 10)
      element = wait.until(EC.presence_of_element_located((By.ID, "myDynamicElement")))
      ```

7. **Closing the Browser**:
    - After completing the interactions, you can close the browser using the `quit` method to end the WebDriver session.
    - Example:
      ```python
      driver.quit()
      ```

### Example Workflow

Here’s a complete example that demonstrates a typical Selenium workflow:

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

# Set up the Chrome driver
driver = webdriver.Chrome(service=Service(ChromeDriverManager().install()))

# Open a website
driver.get("https://www.google.com")

# Find the search box and perform a search
search_box = driver.find_element(By.NAME, "q")
search_box.send_keys("Selenium")
search_box.send_keys(Keys.RETURN)

# Wait for the results to load and display the title
try:
    wait = WebDriverWait(driver, 10)
    wait.until(EC.presence_of_element_located((By.ID, "search")))
    print(driver.title)
finally:
    # Close the browser
    driver.quit()
```

In this example, the script:

1. Sets up the Chrome driver.
2. Opens Google’s homepage.
3. Finds the search box, enters the query "Selenium", and submits the form.
4. Waits for the search results to load.
5. Prints the title of the page.
6. Closes the browser.

This demonstrates the basic capabilities of Selenium for web automation and data extraction.