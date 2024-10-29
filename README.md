# Party Planner

## Overview

The `group-assigner.ipynb` notebook is designed to help organize employees into balanced groups for work parties. It uses the Google Sheets API to read employee data from a template sheet, processes the data to create groups, and writes the results back to a new sheet in the same Google Sheets document. Additionally, it uses the OpenAI API to generate creative group names based on the names of the employees in each group.

## Setup Instructions

### Prerequisites

1. **Python Environment**: Ensure you have Python 3.7+ installed.
2. **Google Sheets API**: Set up a Google Cloud Platform project and enable the Google Sheets API.
3. **OpenAI API**: Obtain an API key from OpenAI.

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/party-planner.git
   cd party-planner
   ```

2. **Install Required Packages**:

   ```bash
   pip install gspread oauth2client pandas openai python-dotenv
   ```

3. **Environment Variables**:

   - Create a `.env` file in the root directory with the following content:
     ```
     GOOGLE_APPLICATION_CREDENTIALS=path/to/your/service-account.json
     GOOGLE_SHEET_URL=https://docs.google.com/spreadsheets/d/YOUR_SPREADSHEET_ID/edit
     OPENAI_KEY=your-openai-api-key
     ```

4. **Share the Google Sheet**:
   - Share your Google Sheet with the service account email found in your `service-account.json` file.

## Input Google Sheet Format

The input Google Sheet should have the following columns:

| Emails                              | Team      | Remote | Attending |
| ----------------------------------- | --------- | ------ | --------- |
| Alice Smith <alice@example.com>     | Sales     | Yes    | Yes       |
| Bob Johnson <bob@example.com>       | Marketing | No     | Yes       |
| Charlie Brown <charlie@example.com> | IT        | Yes    | No        |

- **Emails**: The name and email of the employee.
- **Team**: The team the employee belongs to.
- **Remote**: Whether the employee is remote or not.
- **Attending**: Whether the employee is attending the event.

## Output Google Sheet Format

The output Google Sheet will have group names as headers, with each group containing the employees assigned to it:

| Team Name 1              | Team Name 2                 | Team Name 3             |
| ------------------------ | --------------------------- | ----------------------- |
| Alice Smith (Sales, Yes) | Bob Johnson (Marketing, No) | Charlie Brown (IT, Yes) |
| ...                      | ...                         | ...                     |

- **Team Names**: Generated using the OpenAI API based on the names of the employees in each group.

## Running the Notebook

1. Open `group-assigner.ipynb` in Jupyter Notebook or JupyterLab.
2. Execute the cells in sequence to read the data, create groups, generate group names, and write the results back to the Google Sheet.

## Notes

- Ensure that the Google Sheet is shared with the service account email.
- The OpenAI API is used to generate creative group names. Ensure your API key is valid and has sufficient quota.

This setup will help you efficiently organize and name groups for your work parties using the power of Google Sheets and OpenAI.

---

_Dislaimer: This README (and some of the code) was writen entirely by gpt-4o in Cursor ;)_
