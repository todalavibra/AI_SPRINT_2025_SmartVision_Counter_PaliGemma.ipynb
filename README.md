# AI_SPRINT_2025_SmartVision_Counter_PaliGemma.ipynb

About Google’s Gemma and PaliGemma
Gemma is a family of lightweight, open models developed by Google, optimized for performance, safety, and adaptability. The PaliGemma variant extends Gemma’s capabilities to vision-language tasks—making it ideal for this sprint’s focus on object detection + natural language output.

Key features leveraged in this project:

Multimodal reasoning (image + text).

Support for multilingual prompts and output, enabling integration with African languages.

Efficiency via 4-bit quantization + LoRA fine-tuning, making the model suitable for low-resource deployment.

.

🔍 What the Code Does
1. Setup & Model Loading
Downloads Google’s paligemma-3b-mix-224 model and sets up environment for training using GPU if available.

Applies LoRA adapters to reduce training time and memory requirements.

2. Dataset Generation
Creates a synthetic dataset of images (apples, bananas, oranges) with bounding box annotations.

Converts these into PaliGemma-compatible JSONL format with <loc> tokens and structured prompts.

3. Fine-Tuning
Fine-tunes the model on the dummy dataset for 5 epochs using Hugging Face’s Trainer.

LoRA allows us to efficiently specialize the model without retraining the full architecture.

4. Inference & Object Counting
Runs inference on test images, generating a structured detection string.

Uses the supervision library to parse, count, and annotate detected objects visually.

Annotated images are saved for demonstration and validation.

🌐 Why This Matters
"AI must understand the languages and realities of all people—not just the ones reflected in Western datasets."

Multilingual Potential: With Gemma's language model roots and PaliGemma's image-language alignment, we can localize object detection into Zulu, Swahili, Xhosa, and more.

Contextual Relevance: Many rural or educational users engage in local languages. Our pipeline opens the door for agricultural AI, visual learning aids, and voice assistants in African vernaculars.

Edge Deployment: The final model is optimized to run on low-spec hardware, supporting offline AI use cases in underserved areas.

