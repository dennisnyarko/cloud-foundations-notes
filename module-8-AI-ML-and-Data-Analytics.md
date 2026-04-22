# Introduction to AI and Machine Learning
- Artificial Intelligence is a broad field focused on the development of intelligent computer systems capable of performing humanlike tasks.
- Machine learning is a type of AI for training machines to perform complex tasks without explicit instructions. Machine learning training finds the patterns hidden in vast amounts of historical data to produce an ML model. This ML model can then be applied to new data to make predictions or decisions based on the patterns it's learned.

## Common ML business use cases
ML models power the Amazon.com e-commerce recommendations engine. But ML can solve for lots of other business use cases, such as the following:
- Predict trends, such as future stock prices.
- Make decisions, like routing callers to the right department.
- Detect anomalies, such as bank fraud.

## AWS AI/ML solutions
The AWS AI/ML stack is composed of the following three tiers of solutions:
- AI services: pre-built models that are already trained to perform specific functions.
- ML services: a more customized approach with Amazon SageMaker AI, where you build, train, and deploy your own ML models with fully managed infrastructure.
- ML frameworks and infrastructure: a completely custom approach to building models using purpose-built chips that integrate with popular ML frameworks.

# AWS AI/ML Solutions
## Tier 1: Pre-built AWS AI services
The AWS AI services tier is made up of pre-built models that are already trained to perform specific functions. These ready-to-use, managed services can help you quickly solve for a variety of business use cases.
- Language services
- Computer vision and search services
- Conversational AI and personalization services

## Language Services
- Amazon Comprehend: It uses natural language processing to extract key insights from documents. It develops these insights by recognizing key phrases, language, sentiment, and other common elements in documents. Use cases: Content classification, customer sentiment analysis, and compliance monitoring.
- Amazon Polly: It converts text into lifelike speech. It supports multiple languages, different genders, and a variety of accents. Use cases: Virtual assistants, e-learning applications, and accessibility enhancements for visually impaired users.
- Amazon Transcribe: It converts speech into text. It supports multiple languages and offers features such as speaker identification, custom vocabulary, and real-time transcription. Use Cases: Customer call transcription, automated subtitling, and metadata generation for media content.
- Amazon Translate: It is a text translation service. This service is ideal for global communication because it supports real-time and batch text translation across multiple languages. Use cases: Document translation and multi-language application integrations

## Computer vision and search services
- Amazon Kendra: It uses natural language processing to search for answers within large amounts of enterprise content. Because it understands the context of a query, it can return more precise and relevant answers than just a list of documents with matching keywords. Use cases: Intelligent search, chatbots, and application search integration.
- Amazon Rekognition: It is a video analysis service. It can identify objects, people, text, scenes, and activities within images and videos stored in Amazon Simple Storage Service (Amazon S3). Use cases: Content moderation, identity verification, media analysis, and home automation experiences.
- Amazon Textract: It detects and extracts typed and handwritten text found in documents, forms, and even tables within documents. Use cases: Financial, healthcare, and government form text extraction for quick processing.

## Conversational AI and personalization services
- Amazon Lex: With Amazon Lex, you can add voice and text conversational interfaces to your applications. This service uses both natural language understanding (NLU) and automatic speech recognition (ASR) to create lifelike conversations. Use cases: Virtual assistants, natural language search for FAQs, and automated application bots.
- Amazon Personalize: With Amazon Personalize, you can use historical data to build intelligent applications with personalized recommendations for your customers. Use cases: Personalized streaming, product, and trending recommendations.
