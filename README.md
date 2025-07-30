# Invoice Generator

A modern, responsive invoice generator built with React and Bootstrap. Create, preview, and download professional invoices with ease.

## Features

- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-time Calculations**: Automatic calculation of subtotals, taxes, discounts, and totals
- **PDF Generation**: Download invoices as PDF files using html2canvas and jsPDF
- **Professional Layout**: Clean, modern invoice design with proper formatting
- **Multiple Currencies**: Support for USD, GBP, JPY, CAD, AUD, SGD, CNY, and BTC
- **Editable Fields**: Inline editing for all invoice items and details
- **Tax & Discount Support**: Configurable tax rates and discount percentages
- **Item Management**: Add, edit, and remove invoice items dynamically

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd invoice-generator
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

4. Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## Usage

1. **Fill in Invoice Details**:
   - Set the due date and invoice number
   - Enter billing information (Bill To and Bill From)

2. **Add Items**:
   - Click "Add Item" to add products or services
   - Enter item name, description, quantity, and price
   - Items are automatically calculated

3. **Configure Settings**:
   - Select currency from the dropdown
   - Set tax rate (optional)
   - Set discount rate (optional)

4. **Generate Invoice**:
   - Click "Review Invoice" to preview
   - Download as PDF or send invoice

## Project Structure

```
src/
├── App.js                 # Main application component
├── App.css               # Global styles
├── index.js              # Application entry point
├── index.css             # Base styles
├── reportWebVitals.js    # Performance monitoring
└── components/
    ├── Form.js           # Main invoice form component
    ├── Modal.js          # Invoice preview modal
    ├── Item.js           # Individual invoice items management
    └── Field.js          # Reusable editable input component

public/
├── index.html            # HTML template
├── manifest.json         # PWA manifest
├── robots.txt           # SEO robots file
└── favicon.ico          # Site favicon
```

## Dependencies

- **React**: ^17.0.2 - UI library
- **React Bootstrap**: ^2.0.0-beta.6 - UI components
- **Bootstrap**: ^5.1.0 - CSS framework
- **html2canvas**: ^1.3.2 - HTML to canvas conversion
- **jsPDF**: ^2.3.1 - PDF generation
- **react-icons**: ^4.2.0 - Icon components

## Available Scripts

- `npm start` - Runs the app in development mode
- `npm build` - Builds the app for production
- `npm test` - Launches the test runner
- `npm eject` - Ejects from Create React App (one-way operation)

## Key Components

### InvoiceForm ([Form.js](src/components/Form.js))
The main component that handles:
- Invoice form state management
- Real-time calculations
- Form validation
- Currency selection
- Tax and discount calculations

### InvoiceModal ([Modal.js](src/components/Modal.js))
Displays the invoice preview with:
- Professional invoice layout
- PDF generation functionality
- Print-ready formatting
- Send and download options

### InvoiceItem ([Item.js](src/components/Item.js))
Manages individual invoice items:
- Dynamic item addition/removal
- Inline editing capabilities
- Automatic total calculations
- Item table rendering

### EditableField ([Field.js](src/components/Field.js))
Reusable input component with:
- Bootstrap styling
- Currency prefix support
- Form validation
- Input group formatting

## Customization

### Adding New Currencies
Modify the currency dropdown in [`Form.js`](src/components/Form.js):

```javascript
<Form.Select onChange={event => onCurrencyChange({currency: event.target.value})}>
  <option value="$">USD (United States Dollar)</option>
  <option value="€">EUR (Euro)</option>
  // Add new currency options here
</Form.Select>
```

### Styling
Customize the appearance by modifying:
- [`App.css`](src/App.css) - Global styles and component overrides
- [`index.css`](src/index.css) - Base styles
- Bootstrap classes throughout components

### PDF Generation
The PDF generation is handled in [`Modal.js`](src/components/Modal.js) using:
- `html2canvas` for capturing the invoice
- `jspdf` for PDF creation
- Customizable page size and orientation

## Features in Detail

### Real-time Calculations
The application automatically calculates:
- Subtotals for each item (quantity × price)
- Overall subtotal
- Tax amounts based on percentage
- Discount amounts based on percentage
- Final total

### Form Validation
All required fields are validated:
- Invoice number (required, numeric)
- Due date (required, date format)
- Bill to/from information (required)
- Item details (name, quantity, price)

### Responsive Design
- Mobile-first approach
- Responsive table layouts
- Collapsible sidebar on mobile
- Touch-friendly interface

## Browser Support

This project supports modern browsers including:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Known Issues

- PDF generation requires a modern browser with canvas support
- Large invoices may take longer to generate PDFs
- Print styles may vary across different browsers

## Future Enhancements

- [ ] Save invoices to local storage
- [ ] Template customization
- [ ] Multiple tax rates
- [ ] Client database integration
- [ ] Email integration
- [ ] Invoice numbering automation

## Support

If you encounter any issues or have questions, please open an issue in the repository.
