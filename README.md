# 🏊 Aquatic Venue Maintenance System
    
    A complete QR code-based system for managing pool maintenance readings across multiple properties.
    
    ## 📦 What's Included
    
    - **dashboard.html** - Main data entry dashboard for all properties
    - **view_pool1.html** through **view_pool5.html** - View-only pages for each pool
    - **qr-codes.html** - QR code generator and printer page
    - **Aquatic-Venue-Maintenance-Log.xlsx** - Original Excel template reference
    
    ## 🎯 How It Works
    
    ### For Administrators (Data Entry):
    1. Open **dashboard.html** in your browser
    2. Select a property from the tabs at the top
    3. Choose month/year
    4. Enter maintenance readings for each day
    5. Data auto-saves every 60 seconds (or click Save Data button)
    
    ### For Staff/Visitors (View Only):
    1. Scan the QR code at any pool location
    2. View the maintenance readings for that specific pool
    3. No ability to edit - read-only access
    
    ## 📊 Data Fields (Matching Excel Template)
    
    The system tracks all 13 fields from your Excel template:
    1. Disinfectant Residual
    2. pH
    3. Total Alkalinity
    4. Cyanuric Acid
    5. Water Temperature
    6. Microbiological Testing
    7. Pump Pressure Gauge (PSI)
    8. Pump Vacuum Gauge (inHg)
    9. Flow Meter (GPM)
    10. Filter Pressure Gauge (PSI)
    11. Time of Backwash
    12. Attendance
    13. Remarks
    
    ## 🚀 Deployment Instructions
    
    ### Option 1: GitHub Pages (Recommended - Free)
    
    1. **Create a GitHub account** at https://github.com (if you don't have one)
    
    2. **Create a new repository:**
       - Click the "+" icon → "New repository"
       - Name it something like "pool-maintenance"
       - Make it Public
       - Click "Create repository"
    
    3. **Upload all files:**
       - Click "uploading an existing file"
       - Drag and drop all the HTML files from this folder
       - Click "Commit changes"
    
    4. **Enable GitHub Pages:**
       - Go to Settings → Pages
       - Under "Source", select "main" branch
       - Click Save
       - Your site will be live at: `https://yourusername.github.io/pool-maintenance/`
    
    5. **Update QR Codes:**
       - Open your live site: `https://yourusername.github.io/pool-maintenance/qr-codes.html`
       - Update the Base URL field to: `https://yourusername.github.io/pool-maintenance/`
       - Click "Regenerate QR Codes"
       - Print the page
    
    ### Option 2: Netlify (Easiest Setup)
    
    1. **Go to** https://netlify.com and sign up (free)
    
    2. **Deploy:**
       - Click "Add new site" → "Deploy manually"
       - Drag and drop the entire folder containing all HTML files
       - Netlify will give you a URL like: `https://random-name-12345.netlify.app`
    
    3. **Update QR Codes:**
       - Visit your site's QR codes page
       - Update the Base URL to your Netlify URL
       - Regenerate and print
    
    ### Option 3: Vercel
    
    1. **Go to** https://vercel.com and sign up (free)
    
    2. **Deploy:**
       - Click "Add New" → "Project"
       - Upload your files or connect to GitHub
       - Vercel deploys automatically
    
    3. **Update QR Codes as above**
    
    ### Option 4: Local Testing (Before Deployment)
    
    To test on your computer before deploying:
    
    1. **Install Python** (if not already installed)
    
    2. **Open terminal/command prompt** in the folder with these files
    
    3. **Run a local server:**
       ```bash
       # For Python 3:
       python -m http.server 8000
       
       # For Python 2:
       python -m SimpleHTTPServer 8000
       ```
    
    4. **Open browser** and go to: `http://localhost:8000/dashboard.html`
    
    5. **Test QR codes** at: `http://localhost:8000/qr-codes.html`
    
    ## 📱 Using the System
    
    ### Initial Setup:
    
    1. **Deploy the files** using one of the methods above
    2. **Open the QR codes page** and update the Base URL
    3. **Print the QR codes** and place them at each pool
    4. **Open the dashboard** and configure each property's information:
       - Operator/Service Company
       - Phone number
       - Water volume
       - Flow rates
    
    ### Daily Use:
    
    **Dashboard (Data Entry):**
    - Access via bookmark or URL: `your-site.com/dashboard.html`
    - Switch between pools using tabs
    - Select current month/year
    - Fill in readings for each day
    - Data saves automatically
    
    **View Pages (QR Codes):**
    - Staff scans QR code at pool
    - View-only page opens showing that pool's data
    - Can select different months to view history
    - No editing allowed
    
    ## 💾 Data Storage
    
    - **Storage:** Browser Local Storage (no server required)
    - **Capacity:** Can store years of data
    - **Backup:** Use "Export All Data" button to download JSON backup
    - **Restore:** Keep backup files safe; can be imported if needed
    
    ## 🔒 Important Notes
    
    ### Data Persistence:
    - Data is stored in the browser where you enter it
    - If you clear browser data, readings will be lost (unless backed up)
    - **Regular backups recommended:** Export data monthly
    
    ### Multi-Device Access:
    - Current version uses Local Storage (per-device)
    - Data entered on one computer won't appear on another
    - For true multi-device sync, you'll need a backend (see Upgrade section)
    
    ### Security:
    - View-only pages are truly read-only (no edit capability in code)
    - Anyone with the QR code URL can view readings
    - For password protection, consider upgrading to a backend system
    
    ## 🆙 Upgrading to Database Backend
    
    For multi-device access and better data management, you can upgrade to use:
    
    ### Google Sheets Backend:
    - Free option using Google Sheets as database
    - Real-time sync across devices
    - Requires some JavaScript modifications
    
    ### Firebase/Supabase:
    - Free tier available
    - Real database with authentication
    - More setup required
    
    ### Custom Backend:
    - Full control and features
    - Requires server hosting
    - Best for large organizations
    
    **Need help with upgrades?** I can help you implement any of these options!
    
    ## 🛠️ Customization
    
    ### Adding More Properties:
    Open `dashboard.html` and `qr-codes.html`, find the PROPERTIES array, and add:
    ```javascript
    {
        id: 'pool6',
        name: 'Pool #6',
        operator: '',
        operatorPhone: '',
        waterVolume: '',
        minFlow: '',
        maxFilterFlow: ''
    }
    ```
    
    Then create a new viewer: Copy `view_pool1.html` to `view_pool6.html` and update PROPERTY_ID.
    
    ### Changing Field Names:
    Edit the FIELDS array in all files to match your requirements.
    
    ### Styling:
    All CSS is inline - modify colors, fonts, and layout directly in the HTML files.
    
    ## 📞 Support
    
    If you encounter issues or need help with deployment:
    - Check that all files are in the same directory
    - Ensure the Base URL in QR codes page matches your deployment URL
    - Clear browser cache if changes don't appear
    - Export data regularly as backup
    
    ## 📄 License
    
    Free to use and modify for your organization's needs.
    
    ---
    
    **System Version:** 1.0
    **Created:** January 2026
    **Maintenance Log Template:** Aquatic Venue Maintenance Log (Excel)
    