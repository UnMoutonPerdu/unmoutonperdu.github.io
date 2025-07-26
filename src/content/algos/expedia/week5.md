---
title: 'Expedia Internship - Week 5'
description: 'Internship'
pubDate: 'June 22 2025'
heroImage: ''
tags: ["Internship"]
---

## Week 5 as a SWE Intern at Expedia

I'm excited to share the progress I've made on implementing Retrieval-Augmented Generation (RAG) and integrating dictionaries into our localization service. 

### Monday 16/06

For this first day I made my first RAG implementation which was providing some context by generating translations examples of the words from the requests. However after some search I found out that the service provides a database of dictionaries that I think we could use to provide context to our requests. I have to talk about it and how to use them with my navigator. 

### Tuesday 17/06

After discussions with Normand, we decided to leverage existing dictionaries as input rather than generating variants through GPT. This approach promises to be more efficient and accurate. A significant milestone of this day was adding a new feature to the service UI, allowing users to select specific dictionaries for translation channels based on the chosen language. This required modifications to both the front-end and back-end components.

### Thurday 19/06 

Midweek brought some challenges with dependencies and configuration issues. These roadblocks highlighted the complexity of working in a large, interconnected system. With my navigator's guidance, we resolved issues related to outdated versions and configurations in the Maven configuration file. This experience underscored the importance of thorough system knowledge and the value of collaborative problem-solving.

### Friday 30/05

For the end of the week, I decided to focus on two main tasks: 
1. Integrating dictionary entries into the prompts, considering only words present in the prompt and when the output locale is defined.
2. Developing comprehensive tests for the prompt augmentation process.
I had to make some research about the way everything was process inside the service. In fact, locales and dictionaries are weirdly defined in the service and I have to understand that before building something on top of it.

### End of the week

This week was a bit frustrating because of all the dependencies issues I faced which slowed me down considerably in my project. Now it is solved I know I will be able to be more productive about it during the next week. 

