# Expense Splitter

A lightweight, browser-based application for tracking shared expenses among friends, roommates, or any group. Similar to Splitwise, this app helps you track who paid for what and calculates the simplest way to settle up.

Built by vibe coding using Claude 3.7 Sonnet.

## Features

- **Simple Group Management**: Add and remove group members easily
- **Flexible Expense Tracking**: Record expenses with multiple splitting options
  - Equal splits
  - Percentage-based splits
  - Exact amount splits
- **Smart Settlement**: Calculates the minimum number of transactions needed to settle all debts
- **Detailed Breakdowns**: View itemized summaries for each person
- **Offline-Capable**: Works entirely in your browser with no server required
- **Mobile-Friendly**: Responsive design works on desktop and mobile devices

## Demo

Access the live demo [here](https://apatti.github.io/expense-splitter/).

## Getting Started

### Local Development

1. Clone this repository:

```bash
git clone https://github.com/yourusername/expense-splitter.git
cd expense-splitter
```

2. Open `index.html` in your browser:

```bash
# On macOS
open index.html

# On Linux
xdg-open index.html

# On Windows
start index.html
```

Alternatively, you can use a local development server:

```bash
# Using Python 3
python -m http.server

# Using Node.js
npx serve
```

### Deployment

#### Deploy to GitHub Pages

1. Push this repository to GitHub
2. Go to Settings > Pages
3. Select the main branch as the source
4. Your site will be published at `https://yourusername.github.io/expense-splitter/`

#### Deploy to AWS S3

See the [AWS deployment instructions](AWS-DEPLOYMENT.md) for detailed steps.

## How to Use

### 1. Add Group Members

- Navigate to the "Group Members" tab
- Enter names and click "Add Member"

### 2. Record Expenses

- Go to the "Expenses" tab
- Fill in expense details:
  - Description
  - Amount
  - Who paid
  - Date (defaults to today)
- Choose how to split the expense:
  - Equal: Split evenly among selected members
  - Percentage: Specify what percentage each person pays
  - Exact Amounts: Enter precise amounts for each person
- Click "Add Expense"

### 3. View Summary

- Switch to the "Summary" tab to see:
  - Overall balance for each person
  - Optimized settlement plan
  - Detailed breakdown for each member

## How It Works

### Data Storage

All data is stored in your browser's localStorage. This means:
- No account required
- Your data remains private on your device
- Data persists between sessions in the same browser
- Data does not sync between devices

To transfer to a new device, you would need to export/import your data (feature coming soon).

### Settlement Algorithm

The app uses a greedy algorithm to calculate the minimum number of transactions needed to settle all debts:

1. Identifies who has a positive balance (creditors) and negative balance (debtors)
2. Sorts both groups by the absolute amount (largest first)
3. Creates transactions from the largest debtor to the largest creditor
4. Continues until all debts are settled

## Customization

### Styling

The app uses CSS variables for easy styling. To change the color scheme, edit the `:root` variables in the CSS section of the HTML file:

```css
:root {
    --primary-color: #ff5722;
    --secondary-color: #03a9f4;
    --background-color: #f5f5f5;
    --card-color: #ffffff;
    --text-color: #333333;
    --border-color: #dddddd;
}
```

## Browser Compatibility

Works in all modern browsers:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Limitations

- No cloud sync (data stays in your browser)
- No multi-currency support (yet)
- No user authentication (as requested)

## Future Enhancements

- [ ] Data export/import functionality
- [ ] Multi-currency support
- [ ] Receipt image scanning
- [ ] Recurring expenses
- [ ] Categories and tags for expenses
- [ ] Monthly spending charts

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by [Splitwise](https://www.splitwise.com/)
- Built with vanilla HTML, CSS, and JavaScript
- Vibe coding using Claude Anthropic 3.7 Sonnet
