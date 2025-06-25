---
title: "Week #3"
---

# Week #3

## Implemented MVP Features

During Week #3, the team made significant progress toward implementing core features of the **Killah Writing Companion** MVP, focusing on enhancing the text editor, integrating audio modality, and advancing machine learning capabilities. Below is a detailed list of implemented features and their associated user journeys, along with links to relevant pull requests or issues.

1. **Interactive List Support in Text Editor** (Vlad):
   - Added support for creating and managing lists (bulleted and numbered) within the macOS-native text editor.
   - Ensures seamless integration with the existing NSTextView-based editor, maintaining a caret-centric UI.
   - **User Journey**: As a novelist or journalist, I can now create structured lists within my drafts, improving document organization and readability while maintaining my writing flow.
   - **Relevant PR**: 

2. **Audio Modality Integration** (Polina):
   - Integrated audio input processing to enable voice dictation and command recognition.
   - Implemented embedding generation from audio inputs, allowing the application to convert spoken ideas into structured text.
   - Fixed token streaming issues to ensure smooth real-time text generation from audio inputs.
   - **User Journey**: As a journalist or content creator, I can dictate notes or ideas, and the application will convert them into polished, style-consistent text drafts, streamlining my workflow.
   - **Relevant PR**:

3. **LoRA Adapter Integration for Model Training** (Kira):
   - Added a LoRA (Low-Rank Adaptation) adapter to the model training and inference scripts, enhancing the personalization capabilities of the Gemma 3 4B model.
   - Ensured compatibility with the existing hierarchical LoRA architecture (r=64) for style preservation.
   - **User Journey**: As a fiction writer, I benefit from the model adapting to my unique writing style, ensuring text suggestions align with my established voice.
   - **Relevant PR/Notebook**: 

4. **MLP Projector Training for Audio Processing** (Maxim):
   - Trained an MLP (Multi-Layer Perceptron) projector specifically for audio processing, enabling the model to handle audio-to-text and audio understanding tasks.
   - Used datasets such as LibriSpeech, Common Voice, and Open STT for training.
   - **User Journey**: As a user relying on voice input, I can trust the application to accurately process and convert my spoken ideas into structured text.
   - **Relevant PR**: https://github.com/vladkalinichencko/Killah-Prototype/commit/a2fac512a0dc83f1ffcebcc3b46bf692c437bdc5

5. **User Stories and Market Analysis** (Janna):
   - Developed detailed user stories to refine the target audience and use cases.
   - Conducted extensive market research, analyzing direct competitors (e.g., Grammarly, ProWritingAid) and indirect competitors (e.g., ChatGPT, other AI writing tools) to validate the unique market position of Killah.
   - Identified key differentiators: style preservation, on-device processing for privacy, and voice-to-text workflow.
   - **User Journey**: As a PhD student or content creator, I can rely on Killah to provide personalized, style-consistent assistance without compromising my data privacy.
   - **Relevant Documentation**: https://disk.yandex.ru/d/gOtDVatB0l5FQw

## Demonstration of the Working MVP

The current MVP includes a functional macOS-native text editor with list support, audio input processing, and initial model personalization via LoRA adapters. Below are the planned deliverables to demonstrate the MVP (note: specific screenshots, GIFs, or videos were not provided in the input):



## ML

### Link to the Training Code
- **MLP Projector Training**: [Dataset Processing and Training Setup](https://github.com/vladkalinichencko/Killah-Prototype/commit/200a6be7e136c6567f5da82b069abe1fddfea44d) *(Note: Placeholder link; please provide the specific training script link if available)*.
- **LoRA Adapter Script**: [Colab Notebook](https://colab.research.google.com/drive/ZZ) *(Note: Placeholder link; please provide the specific notebook link for LoRA integration)*.

### Model Training Description
- **Data Used**:
  - **LibriSpeech, Common Voice, Open STT**: Audio datasets used for training the MLP projector to handle audio-to-text tasks. These datasets provide diverse speech samples for robust audio processing.
  - **Text Datasets**: Not explicitly mentioned for Week #3, but likely include user-provided text samples for style personalization (as per Week #1 scope).
- **Training Process**:
  - The MLP projector was trained using A100 GPUs (estimated 85-160 GPU-hours from Week #1).
  - **Improvements**:
    - **Normalization**: Applied proper loss normalization by dividing by gradient accumulation steps, with weight updates only after accumulation.
    - **Learning Rate Scheduling**: Used OneCycleLR for stable training.
    - **Activation Functions**: Incorporated Z-normalization and GELU for improved audio understanding.
    - **Model Architecture**: Increased projector parameters for better performance.
  - **Validation Enhancements**:
    - Added debug prints for 3-5 examples with detailed diagnostics.
    - Conducted error analysis to detect empty, redundant, or insufficient generation.
    - Tracked detailed statistics (e.g., word length, error types).
  - **Console Output Overhaul**:
    - Implemented `print_vanishing()` for intermediate metrics, debug examples, validation results, checkpoints, and graphs to keep the console clean.
    - Ensured the progress bar remains stable and readable, with only critical validation results and events persisting.
  - **Metrics Logging**:
    - Automatically logged all metrics to Weights & Biases (W&B) for real-time monitoring.
    - Targeted significant Word Error Rate (WER) reduction from ~3.0 to 0.2-0.5 (20-50% improvement).
    - Aimed for improved BLEU and ROUGE scores due to enhanced architecture.
  - LoRA fine-tuning was applied to the Gemma 3 4B base model using the Hugging Face Trainer API and Accelerate for efficient training.
- **Model Decision Parameters**:
  - The model uses a 3-layer LoRA architecture (r=64) to adapt the base Gemma 3 4B model for style preservation and audio processing.
  - PersonaPlugs runtime conditioning ensures personalized text generation based on user writing samples.
  - Audio processing relies on a Conformer-based encoder integrated with Apple AudioKit, with the MLP projector handling audio-to-text tasks.
- **Next Steps if WER Remains High**:
  - Fine-tune Gemma with LoRA by unfreezing specific layers.
  - Increase projector dimensionality (e.g., 4096 or 8192).
  - Add more layers (4-5) to the projector.
  - Introduce cross-attention mechanisms between audio and text.

### Links to Initial Model Artifacts
- *(Note: Specific model artifact links were not provided in the input. Please provide links to pre-trained models, weights, or checkpoints if available.)*

## Internal Demo

### Notes from Internal Demo
-



## Weekly Commitments

### Individual Contribution of Each Participant
1. **Janna**:
   - Developed detailed user stories for fiction writers, journalists, and academic writers.
   - Conducted market research, analyzing direct (e.g., Grammarly) and indirect (e.g., ChatGPT) competitors to validate Killah’s unique position.
   - Updated design documentation with new user story insights.
   - **Evidence**: [Market Research and User Stories]

2. **Maxim**:
   - Trained the MLP projector for audio processing using LibriSpeech, Common Voice, and Open STT datasets.
   - Implemented training improvements (e.g., normalization, W&B logging, console output cleanup).
   - **Evidence**: [Dataset Processing Commit]

3. **Kira**:
   - Integrated LoRA adapter into model training and inference scripts.
   - Updated Colab scripts for reproducibility and migrated them to the Git repository.
   - **Evidence**: [Colab Notebook]

4. **Vlad**:
   - Implemented list support (bulleted and numbered) in the NSTextView-based editor.
   - Ensured seamless integration with the existing toolbar and caret functionality.
   - **Evidence**: [List Implementation Commit]

5. **Polina**:
   - Integrated audio modality for voice input and embedding generation.
   - Fixed token streaming for real-time text generation from audio inputs.
   - **Evidence**: [Audio Modality Commit]

## Plan for Next Week

### Development Goals for Week #4
1. **Advanced Text Editor Features**:
   - Implement syntax highlighting and font alignment in the text editor.
   - Add streamed auto-completion for predictive text continuation.
2. **Audio Processing Refinement**:
   - Optimize the audio-to-text pipeline for faster processing and improved accuracy.
   - Add support for voice command recognition (e.g., “start new paragraph”).
3. **Model Personalization**:
   - Enhance PersonaPlugs for better style adaptation based on user writing samples.
   - Validate LoRA adapter performance with user-specific datasets.
4. **UI/UX Improvements**:
   - Iterate on the editor’s UI to support advanced formatting options.
   - Finalize logo design and integrate it into the application.
5. **Testing and Performance**:
   - Conduct performance benchmarks for on-device model execution.
   - Test the MVP with real user scenarios (e.g., dictating a short story or academic abstract).

### Success Metrics
- Fully functional text editor with syntax highlighting and auto-completion.
- Accurate and low-latency audio-to-text conversion.
- Improved style consistency in generated text (measured via user feedback or automated metrics).
- Stable performance on macOS 15 with <8GB memory footprint.
- Successful internal demo showcasing all Week #4 features.

## Confirmation of the Code’s Operability

We confirm that the code in the main branch:
- Is in working condition (not fully free of bugs yet).
- Runs on the intended platform: macOS 15 via Xcode.

If you encounter any problems running the setup, feel free to contact us for assistance. We can also provide a video demonstrating the current state of the prototype upon request.
