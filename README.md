# Puppeteer PDF Generator

Create stunning, dynamic PDFs effortlessly with Node.js, [Handlebars](https://handlebarsjs.com/), and [Puppeteer](https://pptr.dev/). Compile HTML templates with JSON data to generate fully customizable reports with headers, footers, and styles. Ideal for automating document generation in projects. Fast, easy setup!

## Table of Contents

- [Puppeteer PDF Generator](#puppeteer-pdf-generator)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Folder Structure](#folder-structure)
  - [Dependencies](#dependencies)
  - [Customization](#customization)
  - [Contact](#contact)

## Features

- Generates PDFs in portrait mode using Puppeteer.
- Custom headers and footers with dynamic content.
- Reads data from a `data.json` file to populate an HTML template.
- Supports CSS styles, including background colors.
- Creates unique filenames for each generated PDF using a timestamp.
- Ensures proper layout with sufficient margins to avoid header/footer overlap.


## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/dharmeshkanzariya23/puppeteer-pdf-generator.git
   ```

2. Navigate to the project directory:

   ```bash
   cd puppeteer-pdf-generator
   ```

3. Install the required dependencies:

   ```bash
   npm install
   ```

4. Ensure Puppeteer has access to Chrome/Chromium. This will be handled automatically by the Puppeteer package.

## Usage

1. Prepare the JSON data file:

   - Add your data to the `data.json` file. Here's an example structure:
     ```json
     {
       "customer": {
         "name": "John Doe",
         "order": "Winter Collection 2024"
       }
     }
     ```

2. Create an HTML template:

   - Edit the `template.html` file according to your needs. Example:
     ```html
     <div class="content">
       <h1>Welcome, {{customer.name}}</h1>
       <p>Your order: {{customer.order}}</p>
     </div>
     ```

3. Run the PDF generator:

   ```bash
   npm start
   ```

4. Your PDF will be saved in the `pdf` folder with a filename like `John Doe-1627896543210.pdf`.

## Folder Structure

```bash
puppeteer-pdf-generator/
│
├── data.json          # JSON file with dynamic content for the PDF.
├── template.html      # Handlebars HTML template.
├── pdf/               # Folder where generated PDFs are stored.
├── index.js           # Main JavaScript file for PDF generation.
└── package.json       # Project dependencies and scripts.
```

## Dependencies

The project uses the following key packages:

- **[Puppeteer](https://pptr.dev/)**: A Node library that provides a high-level API to control Chrome/Chromium over the DevTools Protocol. It is used for rendering the HTML template into a PDF.
- **[Handlebars](https://handlebarsjs.com/)**: A simple templating engine that allows you to embed dynamic content in the HTML templates.
- **[fs](https://nodejs.org/api/fs.html)**: Node.js core module used to interact with the file system.
- **[path](https://nodejs.org/api/path.html)**: Node.js core module for handling file paths.


## Customization

1. **HTML Template**:
   - Edit the `template.html` file to customize the structure and layout of your PDF content. Handlebars expressions like `{{customer.name}}` are placeholders for dynamic data.

2. **Header & Footer**:
   - Modify the `headerTemplate` and `footerTemplate` strings in `index.js` to customize the header and footer for your PDFs.

3. **CSS Styling**:
   - Add custom styles within the `addStyleTag` method in `index.js` to modify the appearance of the PDF content.

4. **PDF Options**:
   - You can adjust options such as paper size, margins, and whether the background colors are printed by modifying the `options` object in `index.js`.

## Contact

If you encounter any issues, please contact [Dharmesh Kanzariya](mailto:dharmesh.kanzariya23@gmail.com) or create an issue on the [GitHub repository](https://github.com/dharmeshkanzariya23/puppeteer-pdf-generator/issues).