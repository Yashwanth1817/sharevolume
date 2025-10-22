# SEC Shares Outstanding Dashboard

This is a single-page responsive web application that displays the maximum and minimum number of common stock shares outstanding for a given U.S. Securities and Exchange Commission (SEC) CIK (Central Index Key).

## Features

*   **Dynamic Data Display**: Fetches and presents shares outstanding data directly from the SEC XBRL API.
*   **Responsive Design**: Built with Tailwind CSS for optimal viewing across various devices.
*   **Initial Data for Citizens Financial Group**: Defaults to displaying data for Citizens Financial Group (CIK 0000759944) on initial load.
*   **CIK Parameter Support**: Allows users to specify a different CIK via a URL query parameter to dynamically update the displayed information without a page reload.

## How to Use

### Viewing Initial Data (Citizens Financial Group)

Simply open the `index.html` file in your web browser:
`file:///path/to/your/folder/index.html`

### Viewing Data for a Specific CIK

You can append a `?CIK=` query parameter to the URL with a 10-digit CIK to fetch and display data for a different entity.

**Example:**
To view data for the Coca-Cola Company (CIK 0000021344), open:
`file:///path/to/your/folder/index.html?CIK=0000021344`

**Note on Data Filtering:**
The application specifically filters for shares outstanding data where the fiscal year (`fy`) is greater than "2020" and the `val` (value) is a numeric figure. It then identifies the maximum and minimum values from this filtered set.

**Proxy Usage:**
The client-side JavaScript uses a public proxy (`https://api.allorigins.win/get?url=`) to bypass potential CORS restrictions when fetching data directly from the SEC API. For production environments, consider setting up a dedicated, secure proxy.

## Development

### Technologies Used

*   **HTML5**: Structure of the web page.
*   **Tailwind CSS**: Utility-first CSS framework for styling.
*   **JavaScript (ES6+)**: For dynamic data fetching, processing, and UI updates.
*   **SEC XBRL API**: Source for financial data.

### Setup

No special build steps are required. Just open `index.html` in a modern web browser.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
