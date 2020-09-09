# FinTS YNAB Importer

This Python script imports transactions from banks that support the German FinTS Banking API. 

The last 10 days of transactions are imported. It's safe to run this script periodically as duplicates (already imported transactions) are filtered out.

## Settings
Connection details need to be set up in a `settings.json` file in the project folder, see an example at `settings.sample.json`.

- **fints_endpoint**: This is the FinTS endpoint for your bank. An incomplete list of endpoints can be found [here](https://raw.githubusercontent.com/jhermsmeier/fints-institute-db/master/fints-institutes.json).

- **access_token**: A YNAB API access token (Request it in the YNAB [developer settings](https://app.youneedabudget.com/settings/developer))
- **budget_id**: In YNAB's web interface, this is the first ID in the URL
- **account_id**: Transactions are assigned to this account. In YNAB's web interface on the account page, this is the last ID.
- **cash_account_id** (optional): If set, transactions that are identified as cash withdrawls are imported as transfers to this account.

## Install
Install dependencies:
`pip3 install -r requirements.txt`

## Run 
Run the script with:
`python3 fints-to-ynab.py`

