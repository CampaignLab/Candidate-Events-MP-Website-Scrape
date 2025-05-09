# Candidate-Events-MP-Website-Scrape

DISCLAIMER: The Application code script and tool is intended to facilitate research, by authorised and approved parties, pursuant to the ideals of libertarian democracy in the UK, by Campaign Lab membership. Content subject-matter and results can be deemed sensitive and thus confidential. Therefore illicit and authorisation for any other use, outside these terms, is hereby not implied pursuant to requisite UK Data Protection legislation and the wider GDPR enactments within the EU.

BACKGROUND: How political candidates and politicians describe themselves and how they choose to spend their time are both enormously rich data points that can allow us to cut through the noise and understand what the people running our country actually think, what their priorities really are. 

CHALLENGE: Scrape the text and events pages of MPs websites and create a navigable database containing that information so that it can be subject to analysis. 

FOUNDATIONAL SOLUTION:

Here is a complete Scrapy project written in a single Python file that:

I. Creates a Scrapy project structure programmatically.
II. Crawls the two provided URLs to find MP profile pages.
III. Extracts text from those pages and any linked "events" or similar detail pages.
IV. Uses regex to identify personality traits, ideologies, etc. from the text.
V. Stores the data in a JSON file named ukmpprofile2.json.

Below is a visual representation of the Scrapy workflow tailored to your ukmpprofile2_project, which scrapes UK MP profiles and their event pages:

---

🕸️ Scrapy Workflow for ukmpprofile2_project

graph TD
    A[Start: run_ukmpprofile2_scraper.py] --> B[Scrapy Engine]
    B --> C[Scheduler]
    C --> D[Downloader]
    D --> E[Spider: UKMPProfileSpider]
    E --> F[Parse start URLs]
    F --> G{Identify MP Profile Links}
    G -->|TheyWorkForYou| H[parse_mp_profile_twf]
    G -->|Parliament.uk| I[parse_mp_profile_parliament]
    H --> J[Extract MP Details]
    I --> J
    J --> K[Identify Events URLs]
    K --> L[Follow Events URLs]
    L --> M[parse_event_text]
    M --> N[Extract Text Content]
    N --> O[infer_profile]
    O --> P[MPProfileItem]
    P --> Q[Item Pipeline]
    Q --> R[Export to ukmpprofile2.json]

---

🧩 Component Breakdown

Scrapy Engine: Coordinates the data flow between all components.

Scheduler: Queues up requests to be processed.

Downloader: Fetches web pages and feeds them to the engine.

Spider (UKMPProfileSpider): Contains the logic to parse the MP profiles and their event pages.

Item Pipeline: Processes the extracted data and exports it to a JSON file. 

---

📄 Output

The final output is a JSON file named ukmpprofile2.json, containing structured data about each MP's personality profile, social identity, ideological standpoint, and more. 





