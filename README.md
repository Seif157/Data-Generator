🤖 Synthetic Dataset Generator
AI-Powered Synthetic Data Generation with Google Gemini
This project allows you to create high-quality synthetic datasets in seconds using Google's most efficient models. By combining Gemini's high-speed JSON mode with a user-friendly Gradio interface, you can generate realistic data for testing, development, and research.
📥 Installation
1️⃣ Clone the Repository
code
Bash
git clone https://github.com/yourusername/gemini-synthetic-data-generator.git
cd gemini-synthetic-data-generator
2️⃣ Create Virtual Environment (Recommended)
code
Bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
3️⃣ Install Dependencies
code
Bash
pip install -r requirements.txt
Requirements file (requirements.txt):
code
Txt
gradio>=4.0.0
google-generativeai>=0.8.0
pandas>=1.5.0
python-dotenv>=1.0.0
httpx>=0.27.0
4️⃣ Set Up API Key
Create a .env file in the project root:
code
Bash
# .env
GEMINI_API_KEY=your_api_key_here
Note: Get your free API key from Google AI Studio.
🚀 Usage
📓 Running in Google Colab (Recommended)
Since this tool is optimized for Colab:
Open the .ipynb file in Google Colab.
Go to the Secrets (key icon 🔑) in the left sidebar.
Add a secret named GEMINI_API_KEY.
Run the cells to launch the interface.
💻 Running Locally
code
Bash
python app.py
The Gradio interface will launch at http://localhost:7860.
Basic Workflow
Enter API Key (if not in Secrets/Environment).
Describe Your Schema in plain English.
Set Number of Records (supports up to 1000 via batching).
Add Example Format (optional, provides better JSON structure).
Click Generate 🎉.
Download CSV when processing is complete.
📝 Example Schemas
👥 Customer Data
code
Code
Generate customer data with:
- customer_id (format: CUST-XXXX)
- name (full name)
- email (valid email address)
- age (between 18-80)
- city (US cities)
- purchase_amount (between $10-$1000)
- join_date (dates in 2023-2024)
- subscription_type (Free, Basic, Premium)
🛒 E-commerce Products
code
Code
Generate e-commerce product data with:
- product_id (format: PRD-XXXX)
- product_name (creative product names)
- category (Electronics, Clothing, Home, Books)
- price (between $5-$500)
- stock_quantity (between 0-1000)
- in_stock (true/false)
🎯 Advanced Usage
Batch Generation
For datasets larger than 50 records, the tool automatically:
Splits generation into manageable batches.
Uses Gemini's massive context window to maintain consistency.
Combines results into a single consolidated CSV.
High-Speed JSON Mode
This version utilizes Gemini's response_mime_type: application/json configuration. This guarantees that the output is valid JSON without the conversational "fluff" common in other LLMs, leading to a 100% success rate in data parsing.
🔧 Troubleshooting
❌ Error: 404 Model not found
Solution: Google frequently updates model version strings.
Ensure you have the latest library: pip install -U google-generativeai.
The tool defaults to gemini-1.5-flash or gemini-2.0-flash. Check AI Studio to see which models are available in your region.
❌ API Key Not Found
Solutions:
In Colab, ensure you have enabled "Notebook Access" for the GEMINI_API_KEY secret.
Locally, ensure your .env file uses the correct variable name: GEMINI_API_KEY.
❌ Rate Limit Errors (429)
Solutions:
If using the Free Tier, wait 60 seconds between large batch requests.
Reduce the batch_size in the code from 50 to 20.
📊 Output Format
DataFrame Preview
Interactive, scrollable table within the browser.
Displays the first 50 records for instant validation.
CSV Download
Clean, UTF-8 encoded CSV files.
No index column (Pandas default index is removed).
Compatible with Excel, Tableau, PowerBI, and SQL databases.
🧑‍💻 Skill Level
Beginner Friendly ✅
No complex prompting required.
Easy "describe what you want" interface.
One-click CSV export.
💡 Tips for Best Results
Be Specific: Instead of "date," say "dates between 2020 and 2024 in YYYY-MM-DD format."
Use JSON Mode: Always provide the column names in the schema description.
Model Choice: Gemini 1.5 Flash is recommended for its speed; use Gemini 1.5 Pro for extremely complex logical schemas.
🙏 Acknowledgments
Google AI for the Gemini API.
Gradio for the UI framework.
Pandas for the robust data handling.
<div align="center">
Made with ❤️ using Google Gemini
⭐ Star this repo if you find it useful!
</div>