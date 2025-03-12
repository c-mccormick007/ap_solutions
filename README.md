# 🧾 AP Automation Impact Report

## 1. Executive Summary

Upon joining the Accounts Payable department as a temp, the entire process was conducted manually on paper—slow, error-prone, and deeply inefficient. Invoices were physically sorted, printed, and filed with minimal digital infrastructure. As the only remaining team member after my colleague's promotion, I had full control over the workflow and leveraged that opportunity to completely reimagine the system.

I built a custom end-to-end automation suite tailored to our exact needs. This includes an intelligent email processing system with rule-based sorting, OCR-enhanced invoice renaming, a processing queue tracker powered by a SQLite database, check run batching, and automated AS400 macros. From data extraction to remittance generation, nearly every step has been streamlined and digitized.

The results have been dramatic: invoice throughput has more than doubled, manual entry has been virtually eliminated, and error rates have dropped. With stat-tracking embedded in every major script, we now have quantifiable metrics proving the impact of automation. Despite a high invoice volume and systemic inefficiencies outside my control, my automation systems have transformed the AP function into a lean, high-output operation.

---

## 2. Background

When I first started in this department, the AP process relied entirely on manual workflows. Invoices were received via email or mail, then printed, hand-sorted, and physically filed. Payments were processed through paper check runs, with all remittance information organized by hand. The volume of transactions made this process not only inefficient, but unsustainable.

My initial improvements included digitizing the sorting system—moving from paper piles to digital folders. However, even then, the need to print invoices persisted, especially for check runs. When I became the sole person handling AP, I saw the opportunity to build automation tools to eliminate redundancy and improve speed.

This laid the foundation for a full transformation of the department’s operations, turning AP from a bottleneck into a model of automation-driven efficiency.

---

## 3. Automation Solution

The AP automation suite was developed entirely in-house to address the high volume and inefficiencies of the legacy manual process. It consists of multiple integrated components, each designed to handle a specific aspect of invoice processing, vendor communication, and check run preparation.

### 📥 Email Inbox Processor
- Applies custom filtering rules to incoming emails based on sender, subject, and attachment content
- Automatically downloads invoice attachments to the correct queue
- Sorts emails into archival folders
- Eliminates the need for manual inbox monitoring and categorization

### 🧾 Invoice Renamer
- Uses OCR and regular expressions to extract:
  - Invoice number
  - Invoice date
  - Purchase Order (PO) number
- Renames and files invoices into structured folders for consistency and traceability

### ⚙️ One_Button Suite
- Retrieves vendor number based on extracted invoice data
- Updates a custom SQLite database with:
  - Invoice metadata
  - Processing status
- Moves invoices through processing stages:
  - Open / Not Received → Needs to Be Processed
- Ensures a single-click workflow for transitioning invoices through the system

### 🏦 Check Run Suite
- Pulls posted invoices from staging folders
- Sorts them by vendor and check number
- Generates text files with remittance information for each check
- Integrates with AS400 via macro/gui automation to:
  - Select applicable invoices
  - Prepare them for printing in check batches

### 🔍 Statement Viewer & Destroyer
- Statement Viewer bypasses some of AS400's limitations. 
  - One example is when viewing all invoices attached to a PO, you can only view 10 or less entries.
- Statement Destroyer parses vendor statements and:
  - Cross-references against the local invoice database
  - Flags missing, duplicate, or completed invoices
  - Provides instant visibility into the status of all referenced documents

### 🤖 Invoice Entry Automation
- Macro script for AS400 that:
  - Auto-types invoice number, date, and PO
  - Prepares invoices for review and posting
- Greatly reduces manual typing and system navigation time

### 🛠️ Miscellaneous Tools
In addition to the core automation suite, a variety of supplemental tools have been developed to streamline day-to-day workflow, including:

- **HTML to PDF converter** for preserving report formatting and archiving documents
- **AP report generator** that compiles invoice summaries and processing metrics
- Ad hoc scripts designed to improve efficiency across systems and reduce repetitive tasks

These tools, while not part of the primary automation pipeline, further reduce cognitive load and enable faster execution of routine processes.

> 📊 **All major components include built-in stat tracking**, allowing for real-time measurement of script usage, invoice throughput, and bottlenecks. This ensures transparency and provides a data-driven foundation for continual process refinement.

---

## 4. Measurable Impact

Since implementing built-in stat tracking on February 6, 2025, the automation suite has logged substantial activity across all modules. The data below highlights the tangible impact these tools have had on invoice processing, data entry reduction, and time savings.

### 📊 Highlights (Feb 6 – Mar 12, 2025)

| Automation Module            | Key Metrics                                                      |
|-----------------------------|------------------------------------------------------------------|
| **One_Button Suite**         | 3,110 POs processed, 2,828 vendor numbers appended, 394 Crystal Reports avoided |
| **PO Extraction**            | 2,162 POs extracted, 2,411 files moved                           |
| **Quantum Destroyer**        | 553 invoices added to release queue, 310 POs found, 1,860 keystrokes automated |
| **Renamer**                  | 2,631 invoices renamed, 45,292 keystrokes saved                 |
| **AS400 Macro**              | 3,388 invoices posted, 105,257 keystrokes automated              |
| **Check Detail Generator**   | 1,269 text files generated, 807,368 keystrokes eliminated         |
| **Check Sorting Suite**      | 3,810 files sorted, 1,849 checks + 1,680 ACHs + 275 AMEXs sorted |
| **Email Destroyer**          | 3,433 emails destroyed, 2,861 attachments extracted, 1,581 flagged, 230 forwarded |

> ⏱️ **Total Time Saved:** 18 days, 8 hours, 9 minutes, and 7 seconds over 5 weeks

> ⌨️ **Estimated Keystrokes Eliminated:** Over 960,000, significantly reducing risk of repetitive strain and input error

These figures reflect only **five weeks of activity**, illustrating the scale and speed of the impact. With continual use and future expansion, the cumulative effect of this automation is expected to grow exponentially. Check the website [stat website here] for current statistics. 

---

## 5. Cost-Saving Estimates

Based on stat tracking from February 6 to March 12, the automation suite has saved approximately **440.15 labor hours**. At the **median hourly rate for AP Specialists in Chicago ($28.37)**, this equates to:

> ## 💰 **$12,485.08 in labor cost savings** — in just over 5 weeks

This figure does not include:
- Reduced error correction time
- Decreased turnaround for check runs
- Improved vendor response times
- Intangible gains in operational reliability

At the current rate of usage, the automation system is projected to generate **over $120,000/year in time value alone**, nearly the equivalent of two full-time employees. This illustrates a significant return on investment and highlights the operational leverage provided by internally-built automation solutions.

---

## 6. Conclusion

The automation suite I’ve developed has fundamentally transformed the accounts payable process. What began as a paper-based, manual workflow has evolved into a streamlined, high-efficiency system capable of handling thousands of invoices with minimal manual intervention. Every major bottleneck—from email triage to check runs—has been targeted and improved.

In just over five weeks of tracked data, these tools have saved over **440 labor hours**, representing more than **$12,000 in labor cost savings** based on median industry rates. At scale, this impact exceeds **$120,000 annually**, delivering the equivalent output of multiple full-time employees through automation alone.

Despite continued process issues and a high invoice volume, these systems have kept operations running efficiently and consistently. The workload that previously required a team is now being managed by one person—supported by custom-built tooling and strategic process design.

> As the sole creator and operator of this automation infrastructure, I am performing beyond the scope of a traditional AP Specialist. The systems I’ve built demonstrate a clear blend of financial operations expertise and technical development skill—and I am ready to take on even more.

I am proud of what I’ve built. I believe this work reflects not only my value in the present but also my potential moving forward.
