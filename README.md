# Cybratix - Chrome Extension

**Website Security Analysis Tool**

Cybratix provides comprehensive website security analysis with a risk score (0-100) for every website you visit. It analyzes multiple security factors to help you make informed decisions about website safety.

**⚠️ Disclaimer:** Risk scores are based on available data and should be used as one factor in your security assessment. Always use multiple verification methods and consult with security professionals for critical security decisions.

## Features

The extension analyzes websites using IPQualityScore (IPQS) API based on:

- **Domain Age (in days)**: Exact age of the domain in days
- **Fraud Score (0-100)**: Comprehensive fraud risk score (lower is safer)
- **Phishing Detection**: Real-time phishing detection
- **Malware Detection**: Malware and virus scanning
- **Suspicious Activity**: Flags for suspicious behavior patterns
- **Site Safety**: Overall safety assessment

## Installation

1. **Load Extension in Chrome**:
   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode" (toggle in top right)
   - Click "Load unpacked"
   - Select the extension directory

2. **About the Chrome Warning**:
   - You may see: "Chrome recommends you review this extension"
   - This is **normal** for unpacked extensions in Developer Mode
   - The extension is safe - this warning appears for all locally loaded extensions
   - See `CHROME_WARNING_FIX.md` for details and solutions

3. **Verify Installation**:
   - You should see the extension icon in your Chrome toolbar
   - Visit any website to see the risk score badge appear

## Usage

1. The extension automatically analyzes every website you visit
2. A risk score badge appears in the top-right corner of each page
3. The badge shows:
   - Overall risk score (0-100, where 100 is safest)
   - Detailed breakdown of each risk factor
   - Color-coded risk levels (green/yellow/orange/red)
4. For websites with low scores (<50), a warning appears when you interact with forms

## Risk Score Calculation

The risk score is calculated using weighted factors from IPQS data:
- Domain Age: 10%
- Fraud Score: 30% (most important)
- Phishing Detection: 20%
- Malware Detection: 20%
- Suspicious Activity: 10%
- Site Safety: 10%

## API Keys Configuration

**IPQualityScore (IPQS) API is now integrated!** The extension uses IPQS for comprehensive domain analysis including domain age, reputation, phishing detection, and malware scanning.

### IPQS API (Pre-configured)

The extension comes with IPQS API key pre-configured. IPQS provides:
- ✅ Domain age detection
- ✅ Phishing detection
- ✅ Malware detection
- ✅ Fraud score calculation
- ✅ Suspicious activity detection

### Optional: Additional API Keys

You can add additional API keys for enhanced functionality:

1. **Set API keys in Chrome Storage**:
   - Open any website and press F12 to open DevTools
   - Go to Console tab and run:
     ```javascript
     chrome.storage.local.set({
       config: {
         IPQS_API_KEY: '2qxVQ09doSSgHdeDldSlCsLsWMbrxl92', // Already configured
         VIRUSTOTAL_API_KEY: 'your-virustotal-key', // Optional
         WHOIS_API_KEY: 'your-whois-key' // Optional fallback
       }
     });
     ```

2. **Reload the extension** in `chrome://extensions/`

**See `API_KEYS_SETUP.md` for detailed instructions.**

**Note:** 
- IPQS API key is pre-configured and ready to use
- The extension works with IPQS by default
- Additional API keys are optional for enhanced features
- API keys are stored locally in Chrome storage (not synced)

## Privacy

- All analysis is performed server-side through public APIs
- No personal data is collected or stored
- Risk scores are cached locally for 1 hour to reduce API calls

## About

Cybratix analyzes websites using multiple security factors to provide a comprehensive risk assessment:

- Domain age and registration history
- SSL/TLS certificate validation
- Server reputation and malware detection
- WHOIS data analysis
- Phishing pattern detection
- Breach history checking

**Important Notes:**
- Risk scores are calculated based on available data sources
- Use this extension as one tool in your security assessment toolkit
- Results should be combined with other security practices
- The extension is provided "as-is"
- For critical security decisions, consult with security professionals

## Development

### File Structure

```
├── manifest.json          # Extension manifest
├── background.js          # Service worker for risk analysis
├── content.js             # Content script for UI injection
├── popup.html             # Extension popup
├── popup.js               # Popup script
├── styles.css             # Styling for risk badge
└── icons/                 # Extension icons
```

### Building

No build process required. The extension works directly with the source files.

## Developer

**Developed by:** Prince Chukwuemeka  
**Email:** pchukwuemeka424@gmail.com

## License

MIT License - feel free to use and modify as needed.

## Disclaimer

This software is provided "as-is" without any warranties, expressed or implied. The developer makes no claims about accuracy or reliability. Users should use this extension as one tool in their security assessment toolkit and consult with security professionals for critical security decisions.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## Contact

For questions, suggestions, or support, please contact:
- **Email:** pchukwuemeka424@gmail.com
- **Developer:** Prince Chukwuemeka

# cybratix-extention
