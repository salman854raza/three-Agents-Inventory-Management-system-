# AI-Powered Inventory Management System

![System Architecture](https://i.imgur.com/JK9y3dO.png) *(Example architecture diagram - replace with your own)*

## Overview

This is an advanced inventory management system powered by AI (Gemini) with multi-channel notifications (WhatsApp and Email). The system provides real-time inventory tracking, automated alerts, and intelligent suggestions for inventory management.

## Key Features

- 📦 **Inventory Management**:
  - Add, update, and remove products
  - Track quantities and prices
  - Categorize products
- 🤖 **AI Integration**:
  - Get intelligent suggestions for inventory management
  - Conversational interface for queries
- 📱 **Multi-channel Notifications**:
  - WhatsApp alerts for critical events
  - Email reports with attachments
- 📊 **Reporting**:
  - Daily automated reports
  - CSV export functionality
- ⏰ **Automated Monitoring**:
  - Low stock alerts
  - Out-of-stock notifications
  - Scheduled daily reports

## Prerequisites

Before running the system, ensure you have:

1. Python 3.8 or higher installed
2. Required API accounts:
   - [Twilio Account](https://www.twilio.com/) (for WhatsApp notifications)
   - [Google AI Studio](https://ai.google.dev/) (for Gemini API)
   - Email SMTP credentials (Gmail or other provider)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/inventory-management-system.git
   cd inventory-management-system

Create and activate a virtual environment:

bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install dependencies:

bash
pip install -r requirements.txt
Create a .env file in the project root with your credentials:

ini
# Twilio Configuration
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_WHATSAPP_NUMBER=+14155238886
RECIPIENT_WHATSAPP_NUMBER=+923133856076

# Email Configuration
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SMTP_EMAIL=your.email@gmail.com
SMTP_PASSWORD=your_app_password
RECIPIENT_EMAIL=salman854raza@gmail.com

# Gemini AI
GEMINI_API_KEY=your_gemini_api_key
Usage
Run the main system:

bash
python inventory_system.py
Demo Mode
The system includes a demo mode that:

Adds sample products

Simulates sales

Generates reports

Shows notification examples

Manual Operations
You can extend the system by adding manual operations:

python
system = InventorySystem()

# Add a product
system.db.add_product("P005", "Bluetooth Speaker", 20, 49.99, "Electronics")

# Update quantity
system.db.update_quantity("P005", -5)  # Reduce quantity by 5

# Get inventory status
status = system.db.get_inventory_status()
print(status)

# Send custom notification
system.whatsapp_agent.send_message("Custom alert message")
Configuration Options
Customize the system by modifying these aspects:

Monitoring Frequency: Change the sleep time in InventoryManager.monitor_inventory()

Notification Thresholds: Adjust the low stock threshold (currently <10)

Report Timing: Modify the daily report time in the monitor loop

Message Templates: Customize notification messages in the agent classes

Troubleshooting
WhatsApp Not Working
Verify your Twilio number is properly configured for WhatsApp

Ensure your recipient number has joined the Twilio sandbox

Check your account has sufficient balance

Email Not Sending
Verify SMTP credentials are correct

For Gmail, ensure you're using an App Password if 2FA is enabled

Check your email provider's sending limits

AI Not Responding
Verify your Gemini API key is valid

Check your Google AI Studio quota

Ensure you have internet connectivity

File Structure
inventory-system/
├── inventory_system.py      # Main system file
├── README.md                # This documentation
├── .env.example             # Environment variables template
├── requirements.txt         # Dependencies
├── inventory.json           # Inventory data (auto-generated)
└── activity_log.json        # Activity log (auto-generated)
License
This project is licensed under the MIT License - see the LICENSE file for details.

Support
For assistance, please contact:

Email: salman854raza@gmail.com

GitHub: YourUsername


## Additional Recommendations

1. Create a `requirements.txt` file with:
python-dotenv
twilio
google-generativeai


2. Add a `.gitignore` file to exclude:
.env
*.json
pycache/
venv/


3. For production use, consider adding:
- Database integration (MySQL, PostgreSQL)
- Web interface (Flask/Django)
- User authentication
- More robust error handling

This README provides comprehensive documentation for users and developers. You can further customize it based on your specific needs and additional features you implement.
