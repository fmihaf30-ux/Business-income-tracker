# Business Income Allocator & Expense Tracker

A modern, single-file web application for tracking business income, allocating funds across expense categories, and monitoring all transactions. Built with vanilla HTML, CSS, and JavaScript with localStorage persistence.

## 🎯 Features

### Core Functionality
- **Income Tracking**: Add and record income entries with dates
- **Category Management**: Pre-configured expense categories:
  - 💰 Savings
  - 🏠 Rent
  - 👥 Employee Salaries
  - 💡 Utilities
  - ⚙️ Business Operations
  - 📦 Miscellaneous

- **Fund Allocation**: Allocate income across categories with real-time balance updates
- **Transaction Management**: 
  - Remove funds from categories
  - Modify allocations
  - Clear all data with confirmation

### Analytics & Reporting
- **Dashboard Summary**: Quick view of total income, allocated, unallocated, and spent amounts
- **Pie Chart**: Visual breakdown of fund allocation across categories
- **Transaction History**: Complete audit log with filtering by:
  - Transaction type
  - Category
  - Date range
- **CSV Export**: Download transaction history as CSV file
- **JSON Import/Export**: Backup and restore data

### User Experience
- **Undo Functionality**: Revert last action
- **Toast Notifications**: Real-time feedback for all actions
- **Responsive Design**: Works on desktop, tablet, and mobile
- **Data Persistence**: Auto-saves to browser localStorage
- **Optimized Performance**: Single-file vanilla JS (no external dependencies)

## 🚀 Getting Started

### Installation
1. Clone or download the repository
2. Open `business-income-tracker.html` in any modern web browser
3. Start tracking your business income!

### No Dependencies
This application requires:
- A modern web browser (Chrome, Firefox, Safari, Edge)
- No server setup required
- No npm or build tools needed

## 📊 How to Use

### Adding Income
1. Enter the income amount in the "Income Amount" field
2. Select the date received
3. Click "+ Add Income"
4. The amount will appear in the "Unallocated" pool

### Allocating Funds
1. In the Categories section, select a category
2. Click "Allocate" button
3. Enter the amount to allocate
4. Confirm the allocation
5. The amount moves from Unallocated to the category

### Removing Funds (Expenses)
1. Click "Remove" on a category card
2. Enter the amount to remove
3. Confirm removal
4. Amount is deducted and added to "Total Spent"

### Modifying Allocations
1. Click "Modify" on a category card
2. Enter the new allocation amount
3. The balance updates immediately

### Viewing Transaction History
1. Scroll to "Transaction History" section
2. Filter by:
   - **Type**: Income, Allocate, Remove, Modify, Clear
   - **Category**: Select specific category
   - **Date Range**: From and To dates
3. Click "Reset" to clear filters
4. Use "Export CSV" to download history

### Backup & Restore
**Export (Backup)**:
- Click "⬇ Export" button
- Saves current state as JSON file

**Import (Restore)**:
- Click "⬆ Import" button
- Select a previously exported JSON file
- Confirms data restoration

## 🎨 Interface Components

### Summary Dashboard
Four stat cards showing:
- Total Income (green)
- Total Allocated (blue)
- Unallocated funds (orange)
- Total Spent (red)

### Category Cards
Each category displays:
- Category name with icon
- Allocated amount
- Current balance
- Quick action buttons (Allocate, Remove, Modify)
- Recent transaction history

### Charts
- **Pie Chart**: Visual representation of allocation breakdown
- **Quick Stats**: Summary statistics panel

## 💾 Data Structure

All data is stored in browser localStorage under the key `businessIncomeAllocator.v1`. The state includes:
- Total income and spent amounts
- Income entries with timestamps
- Category allocations and balances
- Complete transaction history
- Undo/redo capability

## 🔧 Development

### File Structure
- Single HTML file with embedded CSS and JavaScript
- No external dependencies or imports
- Modular JavaScript functions for maintainability

### Key JavaScript Functions
- `addIncome()` - Add new income entry
- `allocateToCategory()` - Allocate funds to category
- `removeFromCategory()` - Remove/spend funds
- `setAllocation()` - Modify category allocation
- `undoLast()` - Undo previous action
- `renderAll()` - Update entire UI
- `saveState()` / `loadState()` - Persistence

### Customization
To customize categories, edit the `CATEGORY_META` object in the JavaScript section:
```javascript
const CATEGORY_META = {
  savings:       { name: "Savings",           icon: "🏦", color: "#10b981", defaultAllocated: 0 },
  // ... add or modify categories here
};
```

## 🎨 Styling Customization

CSS variables at root level control the design:
```css
:root {
  --primary: #4f46e5;
  --success: #10b981;
  --danger: #ef4444;
  /* ... more variables */
}
```

## 🌐 Browser Support
- Chrome/Chromium (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📱 Responsive Breakpoints
- **Desktop**: Full 3-column layout
- **Tablet** (1024px): 2-column layout
- **Mobile** (640px): Single column layout

## ⚙️ Technical Details

### State Management
- Centralized state object
- Action-based updates with history tracking
- Automatic localStorage persistence
- Graceful error handling

### Performance
- No external library dependencies
- Efficient DOM rendering
- Debounced calculations
- Minimal memory footprint

## 🔒 Data Privacy
- All data stored locally in browser
- No server communication
- No external API calls
- Complete control over your data

## 🐛 Troubleshooting

### Data Not Saving?
- Check if localStorage is enabled in browser
- Try exporting to backup data
- Clear browser cache and reload

### Numbers Displaying Incorrectly?
- Ensure amounts are entered as numbers (no currency symbols)
- Use decimal point for cents (e.g., 1000.50)

### Undo Not Working?
- Undo only works for recent actions
- Refresh page resets undo history

## 📝 License
Open source - feel free to use and modify

## 🤝 Contributing
Suggestions and improvements welcome! Feel free to fork and submit pull requests.

---

**Last Updated**: July 2026
**Version**: 1.0
