
# Feedback-Based Smart Discount System (n8n Workflow)

## Use Case
When a user submits a feedback form, this workflow automatically decides whether they should receive a discount — no manual review needed.
![image alt](https://github.com/Spidy8845/FeedBack-Bases-Discount-n8n/blob/main/Screenshot%202026-07-05%20220637.png?raw=true)
## Workflow: "Feed Back Discount"

**Trigger:** On form submission

**Flow:**
1. **On form submission** — captures the user's feedback response.
2. **If** — checks the feedback value.
   - **true** → routes to **Discount Yes**
   - **false** → routes to **Discount No**
3. **Discount Yes / Discount No** — sets the discount decision (manual node) based on the branch taken.
4. **Append row in sheet** — logs the form response and discount decision into Google Sheets.
5. **Send a message** — sends the discount outcome to the user via Gmail.

## How It Works
1. Form submission triggers the workflow.
2. An IF node checks the feedback.
3. If feedback = Positive → Discount = Yes.
4. If not → Discount = No.
5. All responses are automatically logged into Google Sheets.
6. An email is sent to the user with the discount outcome.

## Benefits
- No manual review
- Instant decision-making
- Clean tracking (all responses logged in Sheets)
- Perfect for e-commerce & loyalty campaigns

## Nodes Used
| Node | Type | Purpose |
|---|---|---|
| On form submission | Form Trigger | Starts the workflow when feedback is submitted |
| If | Conditional | Evaluates feedback sentiment |
| Discount Yes | Set | Marks discount as approved |
| Discount No | Set | Marks discount as not approved |
| Append row in sheet | Google Sheets | Logs the response and decision |
| Send a message | Gmail | Notifies the user of the outcome |


## How to Use the Downloaded JSON Workflow File in n8n
1. Download the workflow's `.json` file form git hub.
2. Open your n8n instance (e.g. `localhost:5678`).
3. Go to **Personal** (or the relevant project) and click **+** to add a new workflow.
4. Click the **...** (three-dot) menu in the top right → select **Import from File**.
5. Choose the downloaded `.json` file and open it — the workflow with all nodes (On form submission, If, Discount Yes/No, Append row in sheet, Send a message) will load onto the canvas.
6. Reconnect credentials for each service node:
   - **Google Sheets** node — select/authenticate your Google account and target spreadsheet.
   - **Gmail** node — select/authenticate your Gmail account.
7. Update the **On form submission** node with your own form fields if needed.
8. Click **Execute workflow** to test it end-to-end.
9. Toggle the workflow to **Published/Active** so it runs automatically on new form submissions.

    
## What This Shows
Automation isn't just about connecting tools — it's about smarter decisions, faster workflows, better documentation, and improved customer experience. From AI-driven developer workflows to marketing automation, the possibilities with n8n are massive.

## Acknowledgment
Special thanks to Nitish Singh Sir for the valuable guidance and support throughout building these workflows.

---
*The goal: let systems handle repetition so we can focus on strategy and creativity.*

