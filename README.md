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
