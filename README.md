# 🎮 Xbox Series X Review Analysis  

This project uses **web scraping, data analysis, and visualization** to explore user reviews of the **Microsoft Xbox Series X** from Best Buy.  

The goal was to collect review text and metadata (ratings, helpful votes, etc.), analyze relationships between review length and helpfulness, and uncover insights into consumer behavior.  

---

## ⚙️ Project Workflow  

### 1. Data Collection (Web Scraping)  
- Used **Selenium WebDriver** (`chromedriver`) to scrape reviews from Best Buy.  
- Extracted **2000 reviews** across ~100 pages.  
- For each review, collected:  
  - `userid`: reviewer name  
  - `review`: review text  
  - `rating`: star rating (out of 5)  
  - `helpful`: number of helpful votes 👍  
  - `unhelpful`: number of unhelpful votes 👎  
  - `net`: |helpful – unhelpful|  
  - `net_helpful`: helpful – unhelpful  
  - `total`: helpful + unhelpful  
  - `review_length`: length of the review (characters)  

First 4 rows:  

| userid  | review                                                                 | rating | helpful | unhelpful | net_helpful | review_length |
|---------|-------------------------------------------------------------------------|--------|---------|-----------|-------------|---------------|
| Andrew  | I used to own an Xbox One X and some people wi...                       | 5      | 75      | 19        | 56          | 1680          |
| EdmondC | Could not wait to pick it up at the store!!! As...                      | 5      | 5       | 0         | 5           | 653           |
| Misphit | I love it, most people are deciding to get one...                       | 5      | 4       | 2         | 2           | 726           |
| Sunday  | After two years of trying, I finally got my ha...                        | 5      | 0       | 0         | 0           | 849           |



---

### 2. Data Analysis  

- **Scatterplot: Review Length vs. Total Votes**  
<img width="511" height="306" alt="Screenshot 2025-08-17 at 4 26 27 PM" src="https://github.com/user-attachments/assets/8bd87634-a716-401f-8a37-6b5962d6fc22" />

    - Best-fit line: slightly upward sloping.  
    - Correlation coefficient: **0.15** → weak positive relationship.  
    - Interpretation: longer reviews get *slightly* more total votes, but the effect is weak.  


- **Scatterplot: Review Length vs. Net Helpful Votes**  
<img width="691" height="303" alt="Screenshot 2025-08-17 at 4 26 50 PM" src="https://github.com/user-attachments/assets/1ec45a63-02f8-49e4-8a54-799ba7dca947" />

    - Best-fit line: almost flat.  
    - Correlation coefficient: **0.03** → essentially no relationship.  
    - Interpretation: longer reviews are not necessarily seen as more helpful.  


---

### 3. Key Findings  

1. **Review length is not strongly tied to helpfulness.**  
   - Longer reviews do not guarantee more helpful votes.  
   - Conciseness may be equally valued by readers.  

2. **User engagement varies widely.**  
   - Some reviews have hundreds of helpful votes, while many get none.  

3. **Surprising outcome.**  
   - The assumption that longer reviews = more helpful votes was **not supported**.  

