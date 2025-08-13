## <b> Description </b>

**Purpose** – The function web_price_data_scrapping() scrapes daily commodity price data for multiple dates from the official FCA Info Web portal.

**Inputs** – Accepts a list of dates (list_of_dates) in the format DD/MM/YYYY for which price reports need to be extracted.

**Selenium Setup** – Uses selenium with Chrome WebDriver in headless mode to automate browser actions without opening a visible browser window.

**Website Navigation** – Programmatically selects the “Price Report” option, chooses “Daily Prices” report type, enters the given date, and triggers the Get Data button.

**Dynamic Content Handling** – Uses WebDriverWait and expected_conditions to ensure that page elements (radio buttons, dropdowns, input fields, tables) are fully loaded before interacting.

**Table Extraction** – Locates the HTML table (id="gv0") containing price data, retrieves its HTML, and parses it with BeautifulSoup.

**Data Cleaning** – Extracts table headers (<th>) and row data (<tr> + <td>), creates a Pandas DataFrame, and filters only relevant commodity columns.

**Date Annotation** – Adds a Date column to tag each row with the corresponding report date for easier analysis later.

**Multiple Dates** – Loops through all given dates, scraping and appending each day’s data into a single output DataFrame.

**Return Value** – Returns the combined DataFrame containing state/UT-wise daily prices for commodities such as Rice, Wheat, Pulses, Edible Oils, Sugar, Vegetables, etc.
