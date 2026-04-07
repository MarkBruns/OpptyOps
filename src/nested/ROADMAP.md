# Roadmap

# **The Agentic Knowledge Architect: A 100-Day Plan for AI-Driven Personal Knowledge Management**

## **Introduction: The Shift to Agentic Development**

This 100-day plan outlines a comprehensive journey to overhaul a Personal Knowledge Management (PKM) system, leveraging the power of agentic AI. This endeavor is framed not as a traditional software project but as a practical immersion into a new paradigm: agentic software development.1 The traditional, imperative model of programming, where a developer explicitly defines every instruction, is giving way to an autonomous model. In this new approach, the developer's role evolves from that of a programmer to an

**AI Conductor** or **System Architect**. The primary task becomes defining high-level goals, establishing objectives, and setting appropriate boundaries within which an intelligent agent can operate autonomously to determine the specific implementation path.3

The success of this 100-day project is contingent upon mastering the art of high-level task decomposition and fostering effective human-AI collaboration. This plan serves as a curriculum for that mastery, using the construction of a world-class PKM system as the practical application. The agentic assistant, exemplified by the open-source Cline extension for VS Code, will not merely assist with code completion but will function as an active development partner, capable of creating files, running terminal commands, and executing complex, multi-step tasks with a degree of autonomy.2

The technology stack has been selected to create a cohesive, integrated ecosystem where each component serves a distinct strategic purpose. Cline acts as the agentic engine, VS Code provides the integrated development environment (IDE), and GitHub serves as the platform for version control, continuous integration/continuous deployment (CI/CD), and project management. The PKM itself will be built upon mdBook, a static site generator implemented in Rust, with the FOAM extension's conventions providing the framework for creating a networked knowledge graph.6 Extensibility will be achieved through Rust for high-performance

mdBook preprocessors and Python for its rich ecosystem of data science and AI libraries. This strategic alignment of technologies is detailed in the table below.

| Component | Category | Strategic Role in Project |
| :---- | :---- | :---- |
| **Cline** | Agentic Coding Assistant | The core "builder" that autonomously executes development tasks based on high-level prompts.4 |
| **VS Code** | Integrated Development Environment | The central "workshop" where all development, agent interaction, and debugging occurs.5 |
| **GitHub** | Collaboration & CI/CD Platform | The "scaffolding" for version control (Repo), automated deployment (Pages, Actions), and task management (Projects).11 |
| **mdBook** | Static Knowledge Base Generator | The foundational technology for creating a modern, searchable, and web-accessible book from Markdown files.6 |
| **FOAM** | Note-Linking Framework | The conceptual model and syntax (\[\[wikilinks\]\]) for creating a networked, Zettelkasten-style knowledge graph.7 |
| **Rust** | Systems Programming Language | The language for building high-performance, custom mdBook preprocessors to extend the PKM's core functionality.13 |
| **Python** | Data Science & Scripting Language | The language for advanced features like Natural Language Processing (NLP), search indexing, and extending Cline's capabilities via MCP.16 |
| **OpenRouter** | LLM API Gateway | A unified interface to access a wide variety of Large Language Models (LLMs), enabling flexibility and cost management.5 |
| **Docker** | Containerization Platform | A tool to create a reproducible development and build environment, ensuring consistency and simplifying setup.20 |
| **Google Jules** | Comparative Agentic Platform | An alternative agentic system for a comparative analysis of different development workflows and architectures.22 |
| **Modular Platform** | High-Performance AI Platform | An exploratory platform (including Mammoth, Mojo, MAX) for investigating future performance optimizations for AI/ML tasks.24 |

## **Phase I: Foundations and Environment Setup (Days 1-20)**

This initial phase is dedicated to constructing a robust "mission control" for the entire 100-day project. The objective is to establish a fully automated, version-controlled, and meticulously structured environment before commencing any significant feature development. This front-loading of infrastructure work is a critical investment that ensures stability and efficiency over the long term. A key principle of this phase is to apply the tools of the project *to* the project itself, creating a virtuous cycle of learning and practical application from the very first day.

### **Week 1: Project Scaffolding (Modules 1-7)**

The first week focuses on creating the digital skeleton of the project. This involves initializing the code repository, setting up the project management tools, and performing an initial manual deployment to understand the end-to-end process.

#### **Modules 1-2: GitHub Repository and Project Initialization**

The foundation begins with a new GitHub repository. To accelerate the setup of the PKM's structure, the project will be bootstrapped using the foam-template.7 This template provides a pre-configured VS Code workspace with recommended extensions (

.vscode/extensions.json) and settings (.vscode/settings.json) optimized for knowledge management tasks, such as Markdown All In One and Prettier.28 Within this repository, a new

mdBook project will be initialized in a dedicated /book subdirectory, creating the initial src directory and SUMMARY.md file that will house the PKM content.6

#### **Modules 3-5: Mission Control with GitHub Projects**

To effectively manage a 100-day endeavor, this entire plan will be translated into a functional project board using GitHub Projects. This approach makes the project plan itself a dynamic, version-controlled artifact. A new GitHub Project will be created, and an issue will be opened for each of the 100 modules. These issues will be organized into phases and categorized using custom fields to track status (e.g., To Do, In Progress, Done), module type (e.g., Setup, Rust, Python, Exploration), and estimated complexity. This immediate application of GitHub Projects transforms project management from a peripheral task into a core component of the learning experience.

#### **Modules 6-7: First Deployment \- Manual CI/CD**

Before automating the deployment process, it is crucial to understand the underlying mechanics. This module involves a manual deployment of the nascent mdBook to GitHub Pages. The repository settings will be configured to deploy from a specific branch, typically gh-pages. The mdbook build command will be run locally to generate the static site in the book/book directory. The contents of this output directory will then be manually committed and pushed to the gh-pages branch. This exercise provides a clear baseline understanding of the build artifacts and the deployment mechanism that will be automated in a later phase.11

### **Week 2: Agent Installation and First Contact (Modules 8-14)**

With the project structure in place, the second week is dedicated to installing, configuring, and establishing a working relationship with the core agentic assistant, Cline.

#### **Modules 8-10: Installing and Configuring Cline**

The primary tool for this project, the Cline VS Code extension, will be installed from the marketplace.4 Configuration is the next critical step. An API key from OpenRouter will be generated and added to the Cline settings.5 OpenRouter serves as a powerful API gateway, providing access to a multitude of LLMs from various providers like Anthropic, Google, and OpenAI.18 Initial experiments will be conducted using different models, such as the powerful

anthropic/claude-3.5-sonnet for complex tasks and the free-tier google/gemini-2.0-flash-exp:free for simpler operations, to gain an intuitive understanding of the cost-performance trade-offs inherent in different models.5

#### **Modules 11-14: Mastering Cline's Core Interactions**

Effective use of an agentic assistant requires learning its interaction patterns. This period will be spent practicing fundamental tasks. Simple, declarative prompts will be used, such as: "Create a new file named TODO.md and add three items," or "Read the README.md file and provide a one-paragraph summary." A crucial distinction to master is the difference between Cline's two primary modes: "Plan" mode, which allows for read-only exploration and task decomposition, and "Act" mode, which executes the proposed changes.33 The "Auto-approve" settings will be explored to understand the balance between the rapid, fluid experience of "vibe coding" and the safety and control of manually approving each step.33 Finally, Cline's ability to interact with the integrated terminal will be tested by instructing it to run commands like

ls \-R to recursively list the project's file structure, confirming its ability to observe and interact with its environment.4

### **Week 3: Full Automation with GitHub Actions (Modules 15-20)**

The final week of the foundational phase focuses on automating the entire build and deployment pipeline, transitioning from the manual process established in Week 1 to a fully autonomous CI/CD workflow. This task itself will be delegated to the agent, serving as a perfect, self-contained test of its capabilities.

#### **Modules 15-20: Building the CI/CD Pipeline**

Instead of manually authoring a YAML configuration file, a high-level, declarative prompt will be given to Cline. For example: "Create a GitHub Actions workflow file at .github/workflows/deploy.yml. This workflow must trigger on every push to the main branch. It should set up a Rust environment, install a specific version of mdBook, execute the mdbook build command, and then use the peaceiris/actions-gh-pages action to deploy the contents of the ./book/book output directory to the gh-pages branch."

This approach forces a shift in thinking from syntactic detail to strategic intent. Cline will generate a plan and the corresponding YAML file for review and approval.12 Once the generated workflow file is committed and pushed to the

main branch, the GitHub Actions runner will be triggered. The successful execution of this workflow will confirm that the site is now being built and deployed automatically. Any errors encountered in the runner's logs will be fed back to Cline for troubleshooting, further simulating a real-world human-AI collaborative debugging session. As a final step, the output.html.site-url setting in book.toml will be configured to ensure that the auto-generated 404 page links correctly within the GitHub Pages environment.11

## **Phase II: Core PKM Enhancements via Agentic Rust Development (Days 21-50)**

This phase represents the core of the project, where the PKM system is actively built out with custom features. The primary method will be directing Cline to develop mdBook preprocessors in Rust. The mdBook preprocessor architecture provides an ideal "bounded decision space" for an agent to operate within.3 It has a clearly defined interface—receiving a JSON representation of the book on

stdin and returning a modified version on stdout—a specific language (Rust), and a clear build/test cycle (cargo build). This structure transforms the complex task of software engineering into a series of discrete, measurable, and agent-friendly modules, mitigating risk and making progress verifiable.13

### **Week 4: Introduction to Rust and Preprocessors (Modules 21-27)**

Before building complex features, a foundational understanding of Rust and the preprocessor mechanism is necessary. This will be achieved by having Cline act as both a coder and a tutor.

#### **Modules 21-24: Rust Fundamentals through Cline**

The initial foray into Rust will be guided by the agent. A /scratch directory will be created for experimentation. Prompts will be structured to elicit both code and explanation, such as: "Create a new Rust project in /scratch named rust\_basics. Write a 'Hello, World\!' program. Now, modify it to read a line of text from the user and print it back. In your response, explain the concepts of let, mut, String, and the :: operator." Cline's terminal integration will be used to compile and run the code with cargo run, providing immediate feedback.

#### **Modules 25-27: The Preprocessor "Hello, World\!"**

The next step is to have Cline create a skeleton mdBook preprocessor. The prompt will be specific and reference the official documentation: "Following the mdBook preprocessor development guide, create a new Rust binary crate named mdbook-nop. Implement the Preprocessor trait to create a no-op preprocessor. This program should parse the book JSON from stdin and write the unmodified book JSON back to stdout. Finally, add the necessary configuration to the project's book.toml file to enable this preprocessor".13 This establishes a working baseline for all subsequent preprocessor development.

### **Week 5-6: Agentic Solution to the Wikilink Problem (Modules 28-41)**

The first major feature to be implemented is support for \[\[wikilinks\]\], a cornerstone of modern networked note-taking tools like Foam and Roam Research.7

#### **Modules 28-35: Building the Wikilink Preprocessor**

This multi-step task will require iterative guidance. The initial prompt will be: "Modify the mdbook-nop preprocessor, renaming the crate to mdbook-wikilink. The goal is to parse the content of each book chapter. Use the regex crate to find all occurrences of the pattern \]. For each match, convert it into a standard Markdown link in the format (./some-note-title.md). The link destination must be a 'slugified' version of the note title (lowercase, with spaces replaced by hyphens)."

Cline will propose a plan, which will include adding the regex crate to Cargo.toml. The user will review the generated Rust code (presented as a diff) and provide feedback. The logic will be implemented within the run method of the Preprocessor trait. The user will test the functionality by adding sample wikilinks to their markdown files and running mdbook build, inspecting the generated HTML to verify the transformation. Edge cases, such as aliased links like \], will be addressed in subsequent prompts.

#### **Modules 36-41: Refining and Testing the Preprocessor**

With the basic functionality working, the focus shifts to robustness and quality. A follow-up prompt will be: "The mdbook-wikilink preprocessor is functional but fragile. Enhance it with logic to check if the target file (e.g., some-note-title.md) actually exists within the src directory. If the target file is missing, the generated link should be given a specific CSS class, such as class='broken-link', to allow for distinct visual styling. Additionally, write unit tests using Rust's \#\[test\] attribute to verify the slugification logic for various inputs." This task requires the agent to interact with the filesystem using Rust's std::path::Path module, demonstrating a more advanced capability.

### **Week 7: Generating a Knowledge Graph (Modules 42-50)**

This week focuses on implementing two advanced PKM features: automatic backlink generation and tag indexing.14 Generating backlinks presents a unique challenge that requires a more sophisticated architecture than a single-pass preprocessor. To inject a list of backlinks into a page, the system must first have a complete map of all links across the entire book. A standard preprocessor, which processes chapters sequentially, cannot know about links from chapters it has not yet seen. The solution is a two-pass system, a classic compiler design pattern that can be orchestrated agentically.

#### **Modules 42-47: The Backlink Generator (Two-Pass System)**

The problem is decomposed into two distinct, agent-driven tasks:

1. **Pass 1 (Collection):** A prompt will be given to create the first preprocessor: "Create a new Rust preprocessor named mdbook-link-collector. In its run method, it must iterate through every chapter and parse the content to find all wikilinks. It should build an in-memory data structure, like a HashMap\<String, Vec\<String\>\>, that maps each link target to a list of the source file paths that link to it. After processing all chapters, this preprocessor must serialize the data structure to a JSON file named link\_graph.json in the book's root directory. Crucially, this preprocessor should not modify the book's content."  
2. **Pass 2 (Injection):** A second prompt will define the next stage: "Create a second preprocessor, mdbook-backlink-injector. In the book.toml file, ensure it is configured to run *after* the mdbook-link-collector. In its run method, it must first read and deserialize the link\_graph.json file. Then, for each chapter it processes, it should look up its own path in the loaded link graph. If any backlinks are found, it must append a 'Backlinks' section to the end of the chapter's content, formatted as a Markdown list of links to the source pages."

#### **Modules 48-50: The Tag Indexer**

The final feature of this phase is a tag index. The agentic task will be: "Create a new preprocessor named mdbook-tag-indexer. It must scan all markdown files for tags, which can be denoted by hashtags (e.g., \#project-management) or defined in YAML frontmatter. After collecting all tags and the pages they appear on, it should generate a new virtual chapter, tags.md, and add it to the book. This new chapter should contain an alphabetized index of all tags, with each tag followed by a list of links to the corresponding pages."

## **Phase III: Advanced AI and Python Ecosystem Integration (Days 51-80)**

This phase shifts focus from the Rust-based structural enhancements to integrating the intelligence and analytical power of the Python ecosystem. A key capability of an advanced agent like Cline is its ability to operate as a polyglot programmer, orchestrating interactions between different languages. This phase will leverage that skill by directing Cline to write Python for high-level logic (e.g., search indexing, NLP) and Rust for the low-level integration needed to connect these Python scripts into the mdBook build process. This mirrors sophisticated, real-world software architectures and provides a strenuous test of the agentic workflow.

### **Week 8: Building a Full-Text Search Engine (Modules 51-60)**

While mdBook has built-in search, a custom solution offers greater flexibility and serves as an excellent integration project. The Python library Whoosh is a fast, pure-Python search library ideal for this purpose.39 The integration will be a two-part process, bridged by a Rust preprocessor.

#### **Modules 51-55: Agentic Python Scripting with Whoosh**

The first task is to have Cline write the core indexing logic in Python. The prompt will be: "Create a new Python script at scripts/indexer.py. This script must use the Whoosh library. It needs to define a search schema with fields for path, title, and content, where content is the main searchable text. The script should be able to walk the book/src directory, read the content of each .md file, and add it as a document to a Whoosh index that it creates in a new book/search\_index directory".39

#### **Modules 56-60: Integrating Python and Rust**

With the Python indexer script complete, the next step is to integrate it into the mdBook build lifecycle. This requires a Rust preprocessor to act as an orchestrator. The agentic task is: "Create a new Rust preprocessor crate named mdbook-search-indexer. The sole purpose of this preprocessor is to execute the python scripts/indexer.py command during the mdbook build process. Use Rust's std::process::Command module to run the script. Ensure that the preprocessor correctly handles the working directory and that any errors or non-zero exit codes from the Python script are propagated, causing the mdBook build to fail." The final part of this module would involve having Cline write the necessary client-side JavaScript for the mdBook theme to query this new search index.

### **Week 9-10: NLP-Powered Knowledge Discovery (Modules 61-75)**

This section leverages Python's powerful NLP libraries, particularly spaCy, to automatically extract metadata and generate insights from the raw text of the PKM notes.43 This adds a layer of intelligence that can surface connections and categorize information without manual effort.

#### **Modules 61-68: Named-Entity Recognition and Auto-Tagging**

The goal is to automatically identify and tag key entities within notes. The agentic task will be: "Create a Python script scripts/nlp\_processor.py that uses the spaCy library. The script must accept a markdown file path as a command-line argument. It should load the file, extract the plain text, and process it with one of spaCy's pre-trained models (e.g., en\_core\_web\_sm) to perform Named-Entity Recognition (NER). For each entity recognized (such as PERSON, ORG, GPE), it should generate a corresponding tag. The script should output a JSON object containing a list of these discovered tags".43 A subsequent task will direct Cline to create another Rust preprocessor that runs this script for each file during the build and injects the discovered tags into the file's YAML frontmatter.

#### **Modules 69-75: Automatic Summarization and Keyword Extraction**

Building on the NLP processor, more advanced features will be added. The prompt will be: "Enhance scripts/nlp\_processor.py. Add a function that generates a concise, one-paragraph summary of the input text. Add another function that extracts the top 5 most relevant keywords using a method like TF-IDF or by analyzing noun chunks. The script's JSON output should be updated to include these new fields: summary and keywords." This will likely involve exploring more of the spaCy or Scikit-learn ecosystems.16 The results can then be integrated via a preprocessor to create index pages that display summaries for quick topic overviews, significantly improving the discoverability of knowledge within the system.

### **Week 11: Extending the Agent Itself with MCP (Modules 76-80)**

This week marks a pivotal transition: moving from being a *user* of the agent's tools to a *creator* of new tools for the agent. The Model Context Protocol (MCP) allows developers to extend an agent's capabilities by exposing new functions it can call.4 This is the ultimate form of customization, graduating from prompting in natural language to programming the agent's core abilities. The ultimate test of the agentic workflow is to have the agent build an extension for itself.

#### **Modules 76-80: Building a Custom PKM Search Tool for Cline**

The prompt for this capstone task will be: "Add a tool that allows you to directly query my PKM's Whoosh search index from our chat. To achieve this, create a Python MCP server using the fastmcp library, as described in its documentation.17 This server must expose a tool named

search\_pkm that accepts a query\_string as an argument. When called, this tool should use the Whoosh library to search the index located at book/search\_index and return the top three search results as a formatted string."

Once Cline has built and the user has launched this MCP server, the interaction model changes. The user can now issue commands like: "Use your search\_pkm tool to find notes related to 'agentic frameworks' and then write a summary of your findings." This closes the loop: the agent is now actively using the very systems and tools that it helped to build, creating a powerful, self-referential development environment.

## **Phase IV: Exploration, Optimization, and Synthesis (Days 81-100)**

The final phase of this 100-day journey is dedicated to advanced topics, ensuring the project's long-term viability, and, most importantly, synthesizing the lessons learned about the agentic development process. The focus shifts from feature creation to system hardening, comparative analysis, and future planning.

### **Week 12: Reproducibility and Comparative Analysis (Modules 81-90)**

This week focuses on making the project robust and portable while also broadening the understanding of the agentic landscape by experimenting with a different tool.

#### **Modules 81-85: Containerizing the Environment with Docker**

To ensure the entire development and build environment is perfectly reproducible, it will be packaged into a Docker container. The docker init command, which automates the creation of Docker assets, is an ideal starting point for an agent.20 The agentic task will be: "Use

docker init to generate a Dockerfile for our project. Modify the generated file to use a multi-stage build.21 The initial 'builder' stage should install the full Rust toolchain and Python with all dependencies. The final, production-ready image should be minimal, containing only the compiled Rust preprocessors, the Python scripts, their dependencies, and the

mdBook binary. Also, create a compose.yaml file that defines a service to run the mdbook serve command and maps the necessary ports for local development."

#### **Modules 86-90: A Comparative Experiment with Google Jules**

To gain a broader perspective on agentic architectures, a comparative analysis will be conducted using Google Jules. Jules represents a different approach: it is an asynchronous, cloud-based agent that interacts with repositories primarily through pull requests.22 The GitHub repository for the PKM project will be connected to Jules. A well-defined, self-contained task previously completed by Cline (e.g., "Add unit tests for the wikilink slugification logic") will be assigned to Jules. The experience will be documented in a new PKM note, comparing and contrasting the two workflows: Jules' asynchronous, PR-driven model versus Cline's synchronous, local, in-editor interaction model. This provides invaluable firsthand experience with the strengths and weaknesses of different agentic systems.

### **Week 13: Future-Proofing and Exploration (Modules 91-100)**

The final week is about looking ahead, finalizing the project, and reflecting on the journey.

#### **Modules 91-95: Exploring High-Performance AI with Modular & Mojo**

This is an exploratory module designed to provide a forward-looking perspective on the future of AI programming. The Modular SDK will be installed, and a "Hello, World\!" program will be written in Mojo, a language designed to combine Python's usability with systems-level performance.26 A prompt will be given to Cline: "Explain the key differences between Python and Mojo, focusing on why Mojo is designed to be significantly faster for AI and machine learning workloads.52" The goal is not to build a new feature but to understand the landscape of high-performance AI computing, which could inform future optimizations of the PKM's NLP and search capabilities.

#### **Modules 96-98: System Hardening and Documentation**

A project is not complete without proper documentation. This task will be delegated to the agent that built the system. The prompt will be: "Perform a comprehensive review of the entire project. Identify any functions in the Rust and Python code that lack documentation comments and add them. Create a new CONTRIBUTING.md file that explains the project's architecture, how to set up the development environment using the Docker container, and the process for building the book. Finally, generate a comprehensive README.md for the root of the repository, detailing the project's purpose, its key features, and how to use them."

#### **Modules 99-100: Synthesis and Future Roadmap**

The final two days are for reflection and planning. A meta-note will be created within the newly built PKM titled "Reflections on 100 Days of Agentic Development." This document will synthesize the key learnings from the journey, including the paradigm shift from programmer to AI conductor, the practical strengths and weaknesses of the Cline-based workflow, and the most effective strategies for decomposing complex problems for an AI agent. To conclude the project, a new board in GitHub Projects titled "PKM v2.0 Roadmap" will be created. This board will be populated with future ideas that emerged during the 100 days, such as integrating a vector database for semantic search, creating a new agentic tool for automatic knowledge graph visualization, or exploring a Mojo-based preprocessor for ultra-fast NLP tasks. This final step ensures the project does not end but rather establishes a clear path for its continued, agent-assisted evolution.

## **Conclusion**

This 100-day plan presents a structured methodology for not only building a highly customized, AI-enhanced Personal Knowledge Management system but also for acquiring deep, practical expertise in the emergent field of agentic software development. The journey is designed to systematically transition the developer's role from a direct implementer of code to a high-level architect and conductor of an autonomous AI agent.

The key takeaways from this proposed plan are threefold:

1. **Decomposition is the Master Skill:** The effectiveness of an agentic workflow is directly proportional to the developer's ability to decompose large, ambiguous goals into a series of clear, verifiable, and self-contained tasks. The modular nature of mdBook preprocessors and the distinct phases of the plan are designed to cultivate this skill.  
2. **The Environment is the Contract:** Establishing a robust, automated, and observable environment (via GitHub, CI/CD, and Docker) is paramount. This environment serves as the "contract" between the human and the AI, providing the necessary guardrails, feedback loops, and verification mechanisms that make autonomous operation both possible and safe.  
3. **Human-AI Collaboration is Iterative:** The process is not a "fire-and-forget" delegation. It is a continuous, iterative dialogue. The developer provides the strategic intent, the agent proposes a tactical plan and implementation, and the developer reviews, refines, and guides the process. Mastering this collaborative loop—knowing when to give precise instructions versus when to allow for more autonomy—is the central learning objective.

By completing this 100-module plan, the end result is not merely a piece of software, but a powerful, self-evolving knowledge system and, more importantly, a profound shift in the mental model of how software is created. The developer emerges not just with a new tool, but with a new, more leveraged, and future-proof way of building. The PKM becomes the first artifact of a new practice, setting the stage for tackling increasingly complex projects through the paradigm of human-AI partnership.

#### **Works cited**

1. Introduction to Agentic Programming Part 1 \- RIIS LLC, accessed September 5, 2025, [https://www.riis.com/blog/introduction-to-agentic-programming-part-1](https://www.riis.com/blog/introduction-to-agentic-programming-part-1)  
2. How is Agentic AI Transforming Code Generation in Modern Development? \- Monetizely, accessed September 5, 2025, [https://www.getmonetizely.com/articles/how-is-agentic-ai-transforming-code-generation-in-modern-development](https://www.getmonetizely.com/articles/how-is-agentic-ai-transforming-code-generation-in-modern-development)  
3. The Agentic AI Design Paradigm: Reshaping How We Build Software \- Destination CRM, accessed September 5, 2025, [https://www.destinationcrm.com/Articles/Web-Exclusives/Viewpoints/The-Agentic-AI-Design-Paradigm-Reshaping-How-We-Build-Software-169958.aspx](https://www.destinationcrm.com/Articles/Web-Exclusives/Viewpoints/The-Agentic-AI-Design-Paradigm-Reshaping-How-We-Build-Software-169958.aspx)  
4. Cline \- Visual Studio Marketplace, accessed September 5, 2025, [https://marketplace.visualstudio.com/items?itemName=saoudrizwan.claude-dev](https://marketplace.visualstudio.com/items?itemName=saoudrizwan.claude-dev)  
5. Getting Started with Cline in VS Code | Egirna Technologies, accessed September 5, 2025, [https://www.egirna.com/blog/news-2/getting-started-with-cline-in-vs-code-22](https://www.egirna.com/blog/news-2/getting-started-with-cline-in-vs-code-22)  
6. rust-lang/mdBook: Create book from markdown files. Like Gitbook but implemented in Rust, accessed September 5, 2025, [https://github.com/rust-lang/mdBook](https://github.com/rust-lang/mdBook)  
7. A personal knowledge management and sharing system for ... \- Foam, accessed September 5, 2025, [https://foambubble.github.io/foam/](https://foambubble.github.io/foam/)  
8. cline/cline: Autonomous coding agent right in your IDE, capable of creating/editing files, executing commands, using the browser, and more with your permission every step of the way. \- GitHub, accessed September 5, 2025, [https://github.com/cline/cline](https://github.com/cline/cline)  
9. What Makes a Coding Agent? \- Cline Blog, accessed September 5, 2025, [https://cline.bot/blog/what-makes-a-coding-agent](https://cline.bot/blog/what-makes-a-coding-agent)  
10. Home · cline/cline Wiki \- GitHub, accessed September 5, 2025, [https://github.com/cline/cline/wiki](https://github.com/cline/cline/wiki)  
11. Continuous Integration \- mdBook Documentation \- GitHub Pages, accessed September 5, 2025, [https://rust-lang.github.io/mdBook/continuous-integration.html](https://rust-lang.github.io/mdBook/continuous-integration.html)  
12. A GitHub Action to automatically build and deploy your mdbook project., accessed September 5, 2025, [https://github.com/XAMPPRocky/deploy-mdbook](https://github.com/XAMPPRocky/deploy-mdbook)  
13. Preprocessors \- mdBook Documentation, accessed September 5, 2025, [https://rust-lang.github.io/mdBook/for\_developers/preprocessors.html](https://rust-lang.github.io/mdBook/for_developers/preprocessors.html)  
14. Foam \- Visual Studio Marketplace, accessed September 5, 2025, [https://marketplace.visualstudio.com/items?itemName=foam.foam-vscode](https://marketplace.visualstudio.com/items?itemName=foam.foam-vscode)  
15. Building code inside an mdbook preprocessor \- Rust Users Forum, accessed September 5, 2025, [https://users.rust-lang.org/t/building-code-inside-an-mdbook-preprocessor/64241](https://users.rust-lang.org/t/building-code-inside-an-mdbook-preprocessor/64241)  
16. Top 30 Python Libraries To Know in 2025 \- Great Learning, accessed September 5, 2025, [https://www.mygreatlearning.com/blog/open-source-python-libraries/](https://www.mygreatlearning.com/blog/open-source-python-libraries/)  
17. How to Build a Python MCP Server to Consult a Knowledge Base \- Auth0, accessed September 5, 2025, [https://auth0.com/blog/build-python-mcp-server-for-blog-search/](https://auth0.com/blog/build-python-mcp-server-for-blog-search/)  
18. OpenRouter API Reference | Complete API Documentation, accessed September 5, 2025, [https://openrouter.ai/docs/api-reference/overview](https://openrouter.ai/docs/api-reference/overview)  
19. llms.txt \- OpenRouter, accessed September 5, 2025, [https://openrouter.ai/docs/llms.txt](https://openrouter.ai/docs/llms.txt)  
20. Develop your Rust application \- Docker Docs, accessed September 5, 2025, [https://docs.docker.com/guides/rust/develop/](https://docs.docker.com/guides/rust/develop/)  
21. A Practical Guide To Containerize Your Rust Application With Docker \- ITNEXT, accessed September 5, 2025, [https://itnext.io/a-practical-guide-to-containerize-your-rust-application-with-docker-77e8a391b4a8](https://itnext.io/a-practical-guide-to-containerize-your-rust-application-with-docker-77e8a391b4a8)  
22. Google Jules: The Complete Guide to Google's AI Coding Agent | Entelligence Blog, accessed September 5, 2025, [https://www.entelligence.ai/blogs/google-jules-free-async-ai-for-debugging-code](https://www.entelligence.ai/blogs/google-jules-free-async-ai-for-debugging-code)  
23. Jules: Google's autonomous AI coding agent \- The Keyword, accessed September 5, 2025, [https://blog.google/technology/google-labs/jules/](https://blog.google/technology/google-labs/jules/)  
24. Intro to Mammoth \- Modular docs, accessed September 5, 2025, [https://docs.modular.com/mammoth/](https://docs.modular.com/mammoth/)  
25. Modular Documentation | Modular, accessed September 5, 2025, [https://docs.modular.com/](https://docs.modular.com/)  
26. The Modular Platform (includes MAX & Mojo) \- GitHub, accessed September 5, 2025, [https://github.com/modular/modular](https://github.com/modular/modular)  
27. foambubble/foam: A personal knowledge management and sharing system for VSCode \- GitHub, accessed September 5, 2025, [https://github.com/foambubble/foam](https://github.com/foambubble/foam)  
28. Recommended Extensions \- Foam, accessed September 5, 2025, [https://foambubble.github.io/foam/user/getting-started/recommended-extensions.html](https://foambubble.github.io/foam/user/getting-started/recommended-extensions.html)  
29. Recommended Extensions | Foam, accessed September 5, 2025, [https://foam-template-gatsby-kb.vercel.app/recommended-extensions](https://foam-template-gatsby-kb.vercel.app/recommended-extensions)  
30. How to deploy mdbook on GitHub \- Stack Overflow, accessed September 5, 2025, [https://stackoverflow.com/questions/60706255/how-to-deploy-mdbook-on-github](https://stackoverflow.com/questions/60706255/how-to-deploy-mdbook-on-github)  
31. Cline Configuration Guide: Quick Setup \- APIpie.ai, accessed September 5, 2025, [https://apipie.ai/docs/Integrations/Coding/Cline](https://apipie.ai/docs/Integrations/Coding/Cline)  
32. OpenRouter API | Documentation | Postman API Network, accessed September 5, 2025, [https://www.postman.com/ai-engineer/generative-ai-apis/documentation/ef6c9qg/openrouter-api](https://www.postman.com/ai-engineer/generative-ai-apis/documentation/ef6c9qg/openrouter-api)  
33. A First Look at CLI aNd Editor (CLINE) | by John Duprey | Thomson Reuters Labs | Medium, accessed September 5, 2025, [https://medium.com/tr-labs-ml-engineering-blog/a-first-look-at-cli-and-editor-cline-c96dbc7a6331](https://medium.com/tr-labs-ml-engineering-blog/a-first-look-at-cli-and-editor-cline-c96dbc7a6331)  
34. Cline AI: A Guide With Nine Practical Examples \- DataCamp, accessed September 5, 2025, [https://www.datacamp.com/tutorial/cline-ai](https://www.datacamp.com/tutorial/cline-ai)  
35. peaceiris/actions-gh-pages: GitHub Actions for GitHub Pages Deploy static files and publish your site easily. Static-Site-Generators-friendly., accessed September 5, 2025, [https://github.com/peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages)  
36. peaceiris/actions-mdbook: GitHub Actions for mdBook (rust-lang/mdBook) ⚡️ Setup mdBook quickly and build your site fast. Linux (Ubuntu), macOS, and Windows are supported., accessed September 5, 2025, [https://github.com/peaceiris/actions-mdbook](https://github.com/peaceiris/actions-mdbook)  
37. starter-workflows/pages/mdbook.yml at main \- GitHub, accessed September 5, 2025, [https://github.com/actions/starter-workflows/blob/main/pages/mdbook.yml](https://github.com/actions/starter-workflows/blob/main/pages/mdbook.yml)  
38. Backlinking \- Foam, accessed September 5, 2025, [https://foambubble.github.io/foam/user/features/backlinking.html](https://foambubble.github.io/foam/user/features/backlinking.html)  
39. Quick start — Whoosh 2.7.4 documentation \- Read the Docs, accessed September 5, 2025, [https://whoosh.readthedocs.io/en/latest/quickstart.html](https://whoosh.readthedocs.io/en/latest/quickstart.html)  
40. Whoosh is a fast, featureful full-text indexing and searching library implemented in pure Python. \- GitHub, accessed September 5, 2025, [https://github.com/whoosh-community/whoosh](https://github.com/whoosh-community/whoosh)  
41. Introduction to Whoosh — Whoosh 2.7.4 documentation, accessed September 5, 2025, [https://whoosh.readthedocs.io/en/latest/intro.html](https://whoosh.readthedocs.io/en/latest/intro.html)  
42. Developing a Text Search Engine using the Whoosh Library in Python \- Tutorialspoint, accessed September 5, 2025, [https://www.tutorialspoint.com/developing-a-text-search-engine-using-the-whoosh-library-in-python](https://www.tutorialspoint.com/developing-a-text-search-engine-using-the-whoosh-library-in-python)  
43. Natural Language Processing With spaCy in Python \- Real Python, accessed September 5, 2025, [https://realpython.com/natural-language-processing-spacy-python/](https://realpython.com/natural-language-processing-spacy-python/)  
44. spaCy · Industrial-strength Natural Language Processing in Python, accessed September 5, 2025, [https://spacy.io/](https://spacy.io/)  
45. NLTK vs spaCy \- Python based NLP libraries and their functions \- Seaflux Technologies, accessed September 5, 2025, [https://www.seaflux.tech/blogs/NLP-libraries-spaCy-NLTK-differences/](https://www.seaflux.tech/blogs/NLP-libraries-spaCy-NLTK-differences/)  
46. 9 Best Python Natural Language Processing (NLP) Libraries \- Sunscrapers, accessed September 5, 2025, [https://sunscrapers.com/blog/9-best-python-natural-language-processing-nlp/](https://sunscrapers.com/blog/9-best-python-natural-language-processing-nlp/)  
47. Containerize Rust Application in 2 Minutes using Docker Init \- DEV Community, accessed September 5, 2025, [https://dev.to/ajeetraina/containerize-rust-application-in-2-minutes-using-docker-init-1ohh](https://dev.to/ajeetraina/containerize-rust-application-in-2-minutes-using-docker-init-1ohh)  
48. Jules, Google's asynchronous AI coding agent, is out of public beta \- The Keyword, accessed September 5, 2025, [https://blog.google/technology/google-labs/jules-now-available/](https://blog.google/technology/google-labs/jules-now-available/)  
49. Get started with Mojo \- Modular docs, accessed September 5, 2025, [https://docs.modular.com/mojo/manual/get-started/](https://docs.modular.com/mojo/manual/get-started/)  
50. Mojo : Powerful CPU+GPU Programming \- Modular AI, accessed September 5, 2025, [https://www.modular.com/mojo](https://www.modular.com/mojo)  
51. Learn to Program in Mojo Tutorial for Beginners \- YouTube, accessed September 5, 2025, [https://www.youtube.com/watch?v=EosPHW2ic9U](https://www.youtube.com/watch?v=EosPHW2ic9U)  
52. Exploring the Power of Mojo Programming Language \- Seaflux Technologies, accessed September 5, 2025, [https://www.seaflux.tech/blogs/mojo-ai-programming-language/](https://www.seaflux.tech/blogs/mojo-ai-programming-language/)  
53. Mojo \- A New Programming Language for AI \- Refine dev, accessed September 5, 2025, [https://refine.dev/blog/mojo-programming-language/](https://refine.dev/blog/mojo-programming-language/)