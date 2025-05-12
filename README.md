<img src="docs & media/images/logoTIMINDMAPGPT-small.png" alt="TI MINDMAP GPT" width="200" height="200"/>

Welcome to TI MINDMAP GPT, an AI-powered tool designed to help produce Threat Intelligence Mindmaps.

**Introducing TI Mindmap**
Navigating through lengthy blog posts, threat intelligence articles, or write-ups can be daunting, especially for cyber threat intelligence teams aiming to extract key insights efficiently. Enter TI Mindmap, a tool accessible through the Streamlit app platform. This service harnesses the power of OpenAI, Azure OpenAI, and MistralAI to transform cumbersome content from URLs, uploaded PDFs, or direct text input into concise, actionable summaries. But it doesn’t stop there. Utilizing sophisticated algorithms, TI Mindmap goes beyond mere text reduction, providing users with insightful encapsulations of crucial points and themes.
TI Mindmap is a tool developed using Large Language Models (LLMs). It's designed to assist cyber threat intelligence teams in quickly synthesizing and visualizing key information from various Threat Intelligence sources.
The app operates on a 'Bring Your Own (LLM) Key' model, allowing users to leverage their own Large Language Models keys for personalized and efficient information processing.
This tool aims to streamline the data analysis process, enabling teams to focus more on strategic decision-making and less on the cumbersome task of data mining.

App: [APP](https://ti-mindmap-gpt.streamlit.app/)

## Table of Contents
- [Project](#project)
- [Features](#features)
- [Known Issues & Considerations](#known-issues--considerations)
- [Blog posts](#blog-posts)
- [Contributing](#contributing)
- [License](#license)

## Project

If you find TI MINDMAP useful, please consider starring the repository on GitHub.

## Features
- **Multiple Input Sources**: Analyze content from URLs, uploaded PDF files, or direct text input. (New)
- **LLM Supported**: OpenAI, Azure OpenAI, MistralAI.
- **Comprehensive Summarization**: AI-generated summaries in markdown format.
- **Versatile Mindmapping**:
    - Generate mind maps using Mermaid.js or MarkMap.
    - Special "Tweet Mindmap" for concise social media sharing.
- **Actionable Intelligence Extraction**:
    - **IOCs Extraction**: Identify Indicators of Compromise with VirusTotal enrichment.
    - **TTPs Analysis**:
        - Extract adversary Tactics, Techniques, and Procedures (TTPs) into an overview table.
        - List TTPs ordered by perceived execution time with improved formatting.
        - Visualize TTPs with a graphic timeline (Mermaid.js).
    - **Threat Scope Report**: Generate a "5 Whats" report, presented as a table, to understand threat scope.
- **Interactive Visualizations**:
    - Embedded MITRE ATT&CK® Navigator layer generation and visualization.
    - Mermaid.live editor integration for mind maps and timelines.
- **AI-Powered Chat**: Engage in a conversation with your Threat Intelligence article/data (based on the processed text, which may be truncated for very long inputs).
- **Detailed PDF Reporting**:
    - Export comprehensive PDF reports of your analysis.
    - Includes: Source information (URL, PDF name, or "Pasted Text"), website screenshot (for URLs), AI summary, main mind map, IOCs table, TTPs overview table, TTPs by execution time, TTPs graphic timeline, and 5 Whats report table. (New)
    - Option for portrait or landscape orientation. (New)
- **Content Management & Handling**:
    - **Flexible Input**: Accepts content via URL scraping, PDF file uploads (text extraction via PyPDF2), and direct text pasting. (New)
    - **Original Content Access**: View and download the full, original input content in a dedicated tab, even if a shortened version was used for AI processing due to length. (New)
    - **Large Input Management**: For very long inputs, the application processes a significant portion of the text for AI analysis to manage performance and token limits, while still providing access to the full original text. (New)
    - **Screenshot Capture**: For URL analysis, capture a screenshot of the source webpage.
- **STIX 2.1 Reporting**: Generate STIX 2.1 bundles (SDOs, SCOs, SROs) with visualization (beta). (The dedicated project [GenAI-STIX2.1-Generator](https://github.com/format81/GenAI-STIX2.1-Generator/) has been merged.)

## Known Issues & Considerations
- **PDF Text Extraction**: Currently, PDF text extraction is performed using PyPDF2. This method does not support Optical Character Recognition (OCR), so text cannot be extracted from image-based PDFs or scanned documents. The quality of extracted text can also vary depending on the PDF's structure.
- **Streamlit `st.download_button` Behavior**: In some Streamlit versions (e.g., 1.35 and potentially others), clicking the `st.download_button` (used for PDF report downloads) can trigger a full app rerun. This might lead to the loss of previously generated on-screen output if the app's state isn't fully preserved and reloaded. While Streamlit has been working on improving such behaviors, it's advisable to test this with your current Streamlit version. The generated PDF itself should download correctly.
- **Large Language Model (LLM) Context Windows**: While the app attempts to manage very long inputs by processing a truncated version for AI analysis, the effectiveness of analysis on extremely large documents depends on the context window and capabilities of the selected LLM and its specific model (e.g., GPT-4 series, Mistral Large).

## Blog posts
1. [Introducing TI Mindmap GPT](https://medium.com/@antonio.formato/introducing-ti-mindmap-gpt-6f433f140488)
2. [Enhancing Cyber Threat Intelligence with TI Mindmap GPT: Integration of Azure OpenAI and advanced features](https://medium.com/microsoftazure/enhancing-cyber-threat-intelligence-with-ti-mindmap-gpt-integration-of-azure-openai-and-advanced-94121ed66ac4)
3. [What’s new in TI Mindmap | Feb 2024](https://medium.com/@antonio.formato/whats-new-in-ti-mindmap-feb-2024-14cf3b383833)
4. [What’s new in TI Mindmap | Mar 2024](https://medium.com/@antonio.formato/whats-new-in-ti-mindmap-mar-2024-3712f38c6dd6)
5. [What’s new in TI Mindmap | April 2024](https://medium.com/@antonio.formato/whats-new-in-ti-mindmap-april-2024-29e1bfb88ae5)
6. [What’s new in TI Mindmap | May 2024](https://medium.com/@antonio.formato/whats-new-in-ti-mindmap-may-2024-3af9e8d90be8)
7. [What’s new in TI Mindmap | Sep 2024](https://medium.com/@antonio.formato/whats-new-in-ti-mindmap-sep-2024-1f3ce3197789)

## Contributing

The project is open to external contributions. Pull requests are welcome.
Here's how you can help:

- **Testing and Feedback**: Try the tool with various input types (URLs, PDFs, pasted text) and share your insights to improve its performance and usability.
- **Improving Prompts**: Help refine the AI prompts for better extraction and accuracy of unstructured cyber threat intelligence data.
- **Extending Functionality**: Build additional features, or improve existing workflows (e.g., enhancing PDF text extraction with OCR, supporting more input formats, advanced handling of very large documents).
- **Open Discussions**: Join the conversation to explore innovative use cases and share your ideas.

Your contributions will help make this project more robust and impactful. Thank you for your support!

## License

[GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/)