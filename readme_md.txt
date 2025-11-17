# ✈️ Airline Price Calculator

A modern desktop application for calculating airline freight rates with dynamic markup and comprehensive rate breakdowns.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Python](https://img.shields.io/badge/python-3.8+-green)
![License](https://img.shields.io/badge/license-MIT-orange)

## 📋 Overview

The Airline Price Calculator helps freight forwarders and logistics professionals quickly calculate shipping costs across multiple airlines. The app supports:

- **Minimum flat-rate pricing** for shipments under 100 kg
- **Per-kilogram rate calculations** for larger shipments
- **Dynamic markup adjustments** for custom pricing
- **Multi-airline comparison** to find the best rates
- **Export functionality** for record-keeping and client quotes

## ✨ Features

### 🎯 Core Functionality
- **Smart Weight Brackets**: Automatically selects the correct pricing tier
  - Minimum (flat rate for <100 kg)
  - 100-299 kg
  - 300-499 kg
  - 500-999 kg
  - 1000+ kg
- **Real-time Calculations**: Instant rate calculations with live updates
- **Flexible Markup**: Adjustable markup percentage per search
- **Comprehensive Results**: Shows base rates, sell rates, and per-kg breakdowns

### 💾 Data Management
- **Excel/CSV Import**: Load airline rate data from templates
- **Auto-load Last File**: Remembers your last-used data file
- **Export Results**: Save search results to Excel or CSV
- **Template Generator**: Built-in tool to create properly formatted rate templates

### 🎨 User Interface
- **Modern Dark Theme**: Professional slate color palette
- **Clean 5-Column Layout**: Airline | Base/kg | Total Base | Sell/kg | Total Sell
- **Intuitive Design**: No training required, user-friendly for all skill levels
- **Responsive Layout**: Optimized 1000x700 window size

## 🚀 Quick Start

### Prerequisites

- **Python 3.8 or higher**
- **Windows, macOS, or Linux**

### Installation

1. **Clone or download** this repository

2. **Install required packages**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the calculator**:
   ```bash
   python airline_calculator.py
   ```

4. **Generate a rate template** (first-time setup):
   ```bash
   python template_generator.py
   ```

## 📊 How to Use

### Step 1: Prepare Your Data

1. Run `template_generator.py` to create a rate template
2. Open `airline_rates_template_YYYYMMDD.xlsx` in Excel
3. Replace sample data with your actual airline rates
4. Save the file

**Template Structure:**
```
Airline Name | POL | POD | Minimum | 100-299 | 300-499 | 500-999 | >999
-------------|-----|-----|---------|---------|---------|---------|-----
Air Cargo    | JFK | LHR | 120.00  | 4.50    | 3.85    | 3.20    | 2.55
```

- **Minimum**: Flat rate for any shipment under 100 kg
- **Other columns**: Per-kg rates that get multiplied by weight

### Step 2: Load Your Data

1. Launch the calculator
2. Click **"📁 Load Data File"**
3. Select your Excel or CSV file
4. The app remembers this file for next time!

### Step 3: Search Rates

1. **Enter Port of Loading (POL)**: e.g., JFK, LAX, ORD
2. **Enter Port of Discharge (POD)**: e.g., LHR, NRT, FRA
3. **Enter Weight (kg)**: e.g., 150
4. **Set Markup (%)**: Default is 2%, adjust as needed
5. Click **"🔍 Search Rates"**

### Step 4: View Results

The app displays all matching airlines with:
- **Base per kg**: Cost per kilogram
- **Total Base**: Total cost before markup
- **Sell per kg**: Price per kilogram (with markup)
- **Total Sell**: Final price to quote customer

### Step 5: Export (Optional)

Click **"💾 Export Results"** to save:
- All search parameters
- Complete rate breakdowns
- Ready for client proposals

## 💡 Examples

### Example 1: Small Shipment (Minimum Rate)
```
Route: JFK → LHR
Weight: 45 kg
Minimum Rate: $120.00
Markup: 2%

Results:
- Base per kg: $2.67 ($120 ÷ 45 kg)
- Total Base: $120.00
- Sell per kg: $2.72
- Total Sell: $122.40
```

### Example 2: Standard Shipment (Per-kg Rate)
```
Route: JFK → LHR
Weight: 150 kg (100-299 bracket)
Rate: $4.50 per kg
Markup: 2%

Results:
- Base per kg: $4.50
- Total Base: $675.00 ($4.50 × 150)
- Sell per kg: $4.59
- Total Sell: $688.50
```

### Example 3: Large Shipment
```
Route: LAX → NRT
Weight: 750 kg (500-999 bracket)
Rate: $3.20 per kg
Markup: 5%

Results:
- Base per kg: $3.20
- Total Base: $2,400.00
- Sell per kg: $3.36
- Total Sell: $2,520.00
```

## 🗂️ File Structure

```
airline-price-calculator/
├── airline_calculator.py          # Main calculator application
├── template_generator.py          # Template creation tool
├── requirements.txt               # Python dependencies
├── README.md                      # This file
├── airline_calculator_config.json # Auto-generated (stores last file path)
└── airline_rates_template_*.xlsx  # Generated rate templates
```

## ⚙️ Configuration

The app automatically saves your preferences in `airline_calculator_config.json`:
- Last loaded data file path
- Auto-loads on startup

No manual configuration needed!

## 📤 Export Format

Exported files include:
```
Airline Name | POL | POD | Weight (kg) | Weight Category | Rate per kg | 
Base Rate (Total) | Base Rate per kg | Markup (%) | Sell Rate (Total) | Sell Rate per kg
```

## 🛠️ Troubleshooting

### "No data loaded" on startup
- **Solution**: The last-used file may have been moved or deleted. Simply load a new file.

### "Failed to load file" error
- **Solution**: Check that column names match exactly (case-sensitive):
  - `Airline Name`, `POL`, `POD`, `Minimum`, `100-299`, `300-499`, `500-999`, `>999`

### "No airlines found for route"
- **Solution**: Verify POL and POD codes match those in your data file

### Missing rates for weight category
- **Solution**: Ensure all rate cells have numeric values (no blank cells)

## 🔄 Updates

### Version 1.0.0 (Current)
- Initial release
- Minimum flat-rate pricing
- 5-column results display
- Auto-load last file
- Excel/CSV export
- Template generator

## 📝 Airport Code Reference

Common IATA airport codes:

| Code | Airport |
|------|---------|
| **JFK** | New York (Kennedy) |
| **LAX** | Los Angeles |
| **ORD** | Chicago (O'Hare) |
| **MIA** | Miami |
| **SFO** | San Francisco |
| **LHR** | London Heathrow |
| **CDG** | Paris Charles de Gaulle |
| **FRA** | Frankfurt |
| **NRT** | Tokyo Narita |
| **HKG** | Hong Kong |
| **DXB** | Dubai |
| **SIN** | Singapore |

## 💻 System Requirements

- **OS**: Windows 7+, macOS 10.12+, or Linux
- **Python**: 3.8 or higher
- **RAM**: 100 MB minimum
- **Storage**: 50 MB for application and data
- **Display**: 1024x768 minimum resolution

## 🤝 Support

For issues or questions:
1. Check the Troubleshooting section above
2. Verify your data file format matches the template
3. Ensure all required packages are installed

## 📄 License

MIT License - Free to use for commercial and personal projects

## 🎯 Best Practices

1. **Keep rate data current**: Update your template regularly
2. **Use consistent airport codes**: Stick to standard 3-letter IATA codes
3. **Backup your data**: Keep copies of your rate templates
4. **Test new rates**: Verify calculations with known values
5. **Export important quotes**: Save results for future reference

## 🚀 Future Enhancements (Roadmap)

- [ ] Multiple currency support
- [ ] Historical rate tracking
- [ ] PDF quote generation
- [ ] Email quote directly to clients
- [ ] Fuel surcharge calculations
- [ ] Multi-language support

---

**Made with ❤️ for the freight forwarding industry**