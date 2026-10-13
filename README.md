# Casino bot

Install: `pip install -r requirements.txt`   |   Run: `python main.py`
config.py me apna BOT_TOKEN rakhna (zip wali config me placeholder hai).
Purani `games.py` delete kar do (ab `games/` folder hai).

## Files
- main.py, utils.py, ui.py, tg.py, database.py, admin.py, fair.py, config.py
- cardimg.py (/start card) | refcard.py (/refer card) | stmtcard.py (/statement card) | qr.py (QR)
- payments.py (/transactions) | referral.py (/refer) | statement.py (/statement)
- reports.py + pdfgen.py (sab PDFs)
- games/ : dice.py, tower.py, mines.py, common.py, registry.py

## User commands (private ones group me chalayein to DM me aate hain)
/bal  /start  /play  /dice /tower /mines
/statement            -> card + pages + Export PDF
/transactions (/payhistory)      /transactionspdf (/paypdf)
/refer   /referpdf

## Admin (/admin)
Users & PDFs: user ID/@username daalo -> Games PDF, Refer PDF, Payments PDF, Statement PDF,
Record Deposit / Withdrawal, Add/Deduct balance.
Settings pages: Branding, Start Card, Bets, Games, Deposit/Withdraw links, Referral System, Statement & History.

## Gateway se jodna (deposit/withdraw data)
    import payments
    payments.add_payment(user_id, "deposit", 25.0, asset="USDT_POLYGON", tx="0x...")
    payments.add_payment(user_id, "withdrawal", 10.0, asset="USDT_POLYGON", tx="0x...", status="Paid")
Withdraw check ke liye: `database.wager_left(user_id)` > 0 ho to withdrawal rok do (referral claim ka wager requirement).
