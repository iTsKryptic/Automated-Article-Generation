Here's a README file for your project:

---

# Blog Post Generator

## Overview

This project is a Python script designed to generate blog posts using the OpenAI GPT-3.5-turbo model, Pinecone for vector search, and various text processing tools. It includes functionality for generating blog topics, creating outlines, and writing full blog posts based on provided data and context.

## Features

- **Generate Blog Topics:** Create blog topics related to a general subject using GPT-3.5-turbo.
- **Generate Outline:** Create a structured outline for a blog post based on a given topic and context.
- **Generate Blog Post:** Write a full blog post section by section using the generated outline and context.
- **PDF to Text Conversion:** Convert PDFs in a directory to text files for use in generating blog content.
- **Database Management:** Load and manage a Pinecone vector database for storing and querying blog-related information.

## Requirements

- Python 3.6+
- OpenAI Python client library
- Pinecone Python client library
- LangChain library
- PyPDF2 library

Install the required libraries using pip:

```bash
pip install openai pinecone-client langchain PyPDF2
```

## Setup

1. **OpenAI API Key:** Set up your OpenAI API key and replace the placeholder in the script:

    ```python
    OPEN_API_KEY = 'your_openai_api_key_here'
    ```

2. **Pinecone API Key:** Set up your Pinecone API key and environment:

    ```python
    pinecone.init(
        api_key="your_pinecone_api_key_here",
        environment="your_pinecone_environment_here"
    )
    ```

3. **Directory Path:** Ensure the directory paths for loading and saving PDF files are correctly set:

    ```python
    path = "path_to_your_pdf_directory"
    ```

## Usage

1. **Reload the Database:** You can reload the Pinecone database with the latest PDFs:

    ```python
    reload_question = input("Do you want to reload the database? (Y/N): ")
    if reload_question == 'Y':
        reload_database()
    ```

2. **Generate Blog Topics:**

    ```python
    general_topic = input("Enter the general topic: ")
    blog_topic = generate_blog_topics(general_topic, qa)
    ```

3. **Generate Blog Outline:**

    ```python
    outline = generate_outline(blog_topic, database, sources)
    ```

4. **Generate Blog Post:**

    ```python
    blog_post = generate_blog_post(general_topic, blog_topic, outline, database, sources)
    ```

5. **Save the Blog Post:**

    ```python
    with open(f"{blog_topic}_blog_post.txt", "w") as file:
        file.write(blog_post)
    ```

## Functions

- `generate_blog_topics(general_topic, knowledge_base_querytool)`: Generates a blog topic based on the general topic and knowledge base.
- `generate_outline(topic, knowledge_base, source_list)`: Creates an outline for a blog post using the topic and knowledge base.
- `generate_blog_post(general_topic, topic, outline, knowledge_base, source_list)`: Generates a full blog post based on the topic, outline, and knowledge base.
- `pdf_to_text(pdf_path, output_path)`: Converts a single PDF to a text file.
- `convert_pdfs_in_directory(directory)`: Converts all PDFs in a directory to text files.
- `reload_database()`: Reloads the Pinecone database with the latest PDFs.
- `agreements_disagreements(knowledge_base, topic, source_list)`: Finds agreements and disagreements between different sources.

## Contributing

Feel free to open issues or submit pull requests if you have improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

Feel free to adjust the paths and placeholders as needed.
