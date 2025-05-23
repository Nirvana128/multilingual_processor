# Multilingual Content Processor

A comprehensive language processing tool that works across multiple languages to translate, analyze, and generate content.

## Overview

The Multilingual Content Processor is designed for global e-commerce platforms and other businesses that need to localize content across multiple languages while maintaining brand voice, technical accuracy, and cultural appropriateness.

### Key Features

- **High-quality translation** with context preservation
- **Cross-lingual summarization** and information extraction
- **Multilingual sentiment analysis** and content classification
- **Language-specific content adaptation** (not just translation)

### Bonus Features

- **Speech recognition and translation** for multiple languages
- **Cultural appropriateness checking** for translated content
- **Multilingual SEO optimization**
- **Visual content localization suggestions**

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/multilingual_processor.git
cd multilingual_processor

# Install dependencies
pip install -r requirements.txt
```

## Quick Start

```python
from multilingual_processor.src.api import default_processor

# Translate content
result = default_processor.translate(
    content="Hello, how are you today?",
    source_lang="en",
    target_lang="es"
)
print(result['translated_text'])  # "Hola, ¿cómo estás hoy?"

# Analyze sentiment
sentiment = default_processor.analyze_sentiment(
    content="I love this product! It's amazing.",
    language="en"
)
print(sentiment['sentiment'])  # "positive"

# Process content through multiple operations
result = default_processor.process_content(
    content="This product is excellent. I highly recommend it.",
    source_lang="en",
    target_lang="fr",
    operations=["translate", "summarize"]
)
print(result['final_content'])  # Summarized French translation
```

## Using Workflows

The Multilingual Content Processor includes predefined workflows for common tasks:

```python
from multilingual_processor.src.orchestration import ServiceOrchestrator

orchestrator = ServiceOrchestrator()

# Execute a predefined workflow
result = orchestrator.execute_workflow(
    workflow_name="cultural_translation",
    content="Our product is the best in the market.",
    source_lang="en",
    target_lang="zh-CN"
)
print(result['final_content'])
```

## Architecture

The system is built with a modular architecture that separates core functionality into independent modules:

- **Core Modules**
  - Translation Engine
  - Summarization Engine
  - Sentiment Analysis Engine
  - Content Adaptation Engine

- **Bonus Modules**
  - Speech Recognition Module
  - Cultural Appropriateness Module
  - SEO Optimization Module
  - Visual Content Localization Module

- **Integration Layer**
  - API Module
  - Service Orchestration

## Module Documentation

### Translation Engine

The Translation Engine provides high-quality translation with context preservation.

```python
from multilingual_processor.src.api import default_processor

# Basic translation
result = default_processor.translate(
    content="Hello world",
    source_lang="en",
    target_lang="fr"
)

# Translation with context preservation
result = default_processor.translate(
    content="The bank is closed today.",
    source_lang="en",
    target_lang="fr",
    options={"context": "financial_institution"}
)
```

### Summarization Engine

The Summarization Engine provides text summarization in the same language or across languages.

```python
from multilingual_processor.src.api import default_processor

# Same-language summarization
result = default_processor.summarize(
    content="Long text to summarize...",
    source_lang="en",
    options={"ratio": 0.3}  # Summarize to 30% of original length
)

# Cross-lingual summarization
result = default_processor.summarize(
    content="Long English text to summarize...",
    source_lang="en",
    target_lang="es",  # Summarize and translate to Spanish
    options={"ratio": 0.3}
)
```

### Sentiment Analysis Engine

The Sentiment Analysis Engine analyzes the sentiment of content in multiple languages.

```python
from multilingual_processor.src.api import default_processor

# Basic sentiment analysis
result = default_processor.analyze_sentiment(
    content="I love this product! It's amazing.",
    language="en"
)

# Detailed sentiment analysis
result = default_processor.analyze_sentiment(
    content="The product is good but the delivery was slow.",
    language="en",
    options={"detailed": True}  # Get aspect-based sentiment
)
```

### Content Adaptation Engine

The Content Adaptation Engine adapts content for specific languages and cultures.

```python
from multilingual_processor.src.api import default_processor

# Adapt content for target language/culture
result = default_processor.adapt_content(
    content="Please click the link below to reset your password.",
    source_lang="en",
    target_lang="ja",
    options={"formality": "formal"}
)
```

### Speech Recognition Module

The Speech Recognition Module provides speech recognition and translation capabilities.

```python
from multilingual_processor.src.api import default_processor

# Speech recognition
result = default_processor.speech_recognition(
    audio_file="path/to/audio.wav",
    language="en"
)

# Speech translation
result = default_processor.speech_translation(
    audio_file="path/to/audio.wav",
    source_lang="en",
    target_lang="fr"
)
```

### Cultural Appropriateness Module

The Cultural Appropriateness Module checks content for cultural sensitivity.

```python
from multilingual_processor.src.api import default_processor

# Check cultural appropriateness
result = default_processor.check_cultural_appropriateness(
    content="Let's celebrate with a toast!",
    source_lang="en",
    target_lang="ar-SA"  # Arabic (Saudi Arabia)
)
```

### SEO Optimization Module

The SEO Optimization Module provides multilingual SEO optimization.

```python
from multilingual_processor.src.api import default_processor

# Optimize content for SEO
result = default_processor.optimize_seo(
    content="Welcome to our online store.",
    source_lang="en",
    target_lang="de",
    options={
        "keywords": ["online shop", "buy online"],
        "region": "DE"
    }
)
```

### Visual Content Localization Module

The Visual Content Localization Module provides suggestions for adapting visual content.

```python
from multilingual_processor.src.api import default_processor

# Get visual localization suggestions
result = default_processor.localize_visual_content(
    content_metadata={
        "colors": ["red", "black", "white"],
        "symbols": ["thumbs up", "clock"],
        "imagery": [
            {"category": "people", "elements": ["business meeting", "handshake"]}
        ]
    },
    source_culture="en-US",
    target_culture="zh-CN"
)
```

## Workflow Examples

### Complete Localization Workflow

This workflow performs comprehensive content localization with all checks.

```python
from multilingual_processor.src.orchestration import ServiceOrchestrator

orchestrator = ServiceOrchestrator()

result = orchestrator.execute_workflow(
    workflow_name="complete_localization",
    content="Our product is the best in the market. Buy now to get 50% off!",
    source_lang="en",
    target_lang="ja",
    options={
        "translate": {"formality": "formal"},
        "cultural_check": {"categories": ["marketing", "promotions"]},
        "seo_optimize": {"keywords": ["product", "discount"]}
    }
)

print(result['final_content'])
```

### Custom Workflow

You can create custom workflows for specific needs.

```python
from multilingual_processor.src.orchestration import ServiceOrchestrator

orchestrator = ServiceOrchestrator()

# Create a custom workflow
custom_workflow = orchestrator.create_custom_workflow([
    {"operation": "translate", "description": "Translate to target language"},
    {"operation": "sentiment", "description": "Analyze sentiment"},
    {"operation": "summarize", "description": "Create summary"}
])

# Execute the custom workflow
result = orchestrator.execute_workflow(
    workflow_name=custom_workflow['workflow']['name'],
    content="Long product description text...",
    source_lang="en",
    target_lang="fr"
)
```

## Advanced Usage

### Language Detection

Automatically detect the language of content.

```python
from multilingual_processor.src.api import default_processor

# Detect language
result = default_processor.detect_language(
    content="Bonjour, comment allez-vous aujourd'hui?"
)
print(result['language'])  # "fr"
```

### Getting Supported Languages

Get the list of languages supported by each module.

```python
from multilingual_processor.src.api import default_processor

# Get supported languages
languages = default_processor.get_supported_languages()
print(languages['translation'])  # List of languages supported for translation
print(languages['sentiment'])    # List of languages supported for sentiment analysis
```

### Available Workflows

Get a list of available predefined workflows.

```python
from multilingual_processor.src.orchestration import ServiceOrchestrator

orchestrator = ServiceOrchestrator()

# Get available workflows
workflows = orchestrator.get_available_workflows()
for workflow in workflows:
    print(f"{workflow['name']}: {workflow['description']}")
```

## Error Handling

The Multilingual Content Processor includes robust error handling.

```python
from multilingual_processor.src.api import default_processor

try:
    result = default_processor.translate(
        content="Hello world",
        source_lang="en",
        target_lang="xx"  # Invalid language code
    )
    
    if not result.get('success', False):
        print(f"Error: {result.get('error', 'Unknown error')}")
except Exception as e:
    print(f"Exception: {str(e)}")
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
