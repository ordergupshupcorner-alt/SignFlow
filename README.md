# SignFlow — Quotation, Billing & Job Management for Flex / Signage Shops

**One file: `signflow.html`. No installation, no internet, no login, no dependencies.**

---

## How to run it

1. Save `signflow.html` anywhere (phone, laptop, USB, Google Drive).
2. Double-click / open with any browser (Chrome, Edge, Safari, Firefox).
3. That's it. It works fully offline; everything you type is stored inside that browser.

Optional: on Android/Chrome open the file → menu → **Add to Home screen** to get an app icon.

---

## First 5 minutes

| Step | Where |
|---|---|
| 1. Fill business name, phone, address, GSTIN, bank/UPI | **Business Settings** |
| 2. Check GST % (default 18), numbering prefixes, terms | **Business Settings** |
| 3. Adjust your selling rates (12 flex/signage rates are preloaded) | **Rate List** |
| 4. Create a customer + your first quotation | **Quotations → + New Quotation** |
| 5. Try everything with fake data | **Backup & Data → Load sample data** |

## The workflow it is built around

```
Enquiry → Quotation → (approve) → Job Card → Design → Printing → Finishing
        → Installation → Completed/Delivered → Invoice → Payment collected
```

Every step is one button: a quote converts into a job card, a job card converts into a tax invoice,
and payments already collected carry forward automatically. Nothing is re-typed.

---

## How calculations work (the part that must never be wrong)

| Unit | Formula |
|---|---|
| **sq.ft** | `Area = Width(in) × Height(in) ÷ 144` per piece, `× Qty`, `× (1 + wastage%)`, `× Rate` |
| **r.ft** | `Length(in) ÷ 12` per piece × Qty × (1 + wastage%) × Rate |
| **pcs** | Qty × Rate |
| **job (lump sum)** | Rate, quantity ignored |

Then: `Subtotal → − Discount (% or ₹) → Taxable → + GST → Round off → Total`.

* **GST auto mode** charges **CGST + SGST** when the customer's state matches your business state,
  and **IGST** when it doesn't. You can also force No GST / CGST+SGST / IGST per document.
* **Inclusive pricing** is supported — the app extracts GST from the rate instead of adding it on top.
* Amounts are rounded to 2 decimals per line; the grand total can round to the nearest rupee
  (toggle in settings). **Amount in words** is generated in Indian format (lakh/crore).
* Payment status is derived from the payment ledger: Unpaid / Part paid / Paid, with overdue detection.

---

## Documents it prints (A4, ready for PDF)

* **Quotation** — validity, terms, advance requested, customer acceptance signature box.
* **Tax Invoice** — HSN/SAC, GST breakup, place of supply, bank + UPI details, balance due, PAID / PART PAID stamp.
* **Job Card** — site, assignee, delivery date, sizes in inches, production checklist, work notes.
* **Payment Receipt** — amount, mode, reference, account position.

Use **Print / PDF** in the app, then choose "Save as PDF" in the browser print dialog.
Documents with many items automatically switch to a compact layout so they fit on one page.

## Customer communication

* **WhatsApp** opens a pre-written message: item sizes, rates, totals, balance, UPI/bank details — send it in one tap.
* **Copy** puts the same summary on the clipboard for SMS or email.
* All documents are printable/shareable as PDF.

---

## Data & safety

* Data is saved automatically to this browser's **localStorage** after every action.
* **Backup & Data → Export backup (.json)** for a full copy; **Import** restores it on any device.
* **CSV export** for invoices, jobs, customers and payments — ready for your CA / Excel.
* Browser data cleared = data lost, unless you have a backup. Export weekly.
* Use one device (your billing machine) as the master; send PDFs to others.

---

## Keyboard

* `Ctrl/Cmd + S` — save the document you are editing
* `Esc` — close any dialog
