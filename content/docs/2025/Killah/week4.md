---
title: "Week #4"
---

# **Week #4**

## Testing and QA

*Summary of testing strategy and types of tests implemented.*

*No information provided regarding testing strategy or test implementation.*

### Evidence of test execution

*Screenshots of test reports, CI logs, code coverage report.*

*No test execution evidence provided.*

## CI/CD

*Description of CI/CD setup, tools used, and any challenges.*

*No information provided regarding CI/CD setup or tools.*

### Links to CI/CD configuration files

*No CI/CD configuration files provided.*

## Deployment

### Staging

*Details about the deployment process, environment setup for staging environment.*

*No information provided regarding staging deployment.*

### Production

*If you focus on bonus points, describe the production deployment process, environment setup for production environment, public domain name and VDS setup.*

*No information provided regarding production deployment.*

## Vibe Check

The team made significant progress in enhancing the application’s functionality and advancing the AI component, though some challenges were encountered. Polina successfully quantized the model and refactored the LLM code, improving maintainability. Vlad faced difficulties with the audio modality training, experiencing mode collapse, and is exploring a new approach to address this. He also worked on application improvements, though some tasks are still in progress. Zhanna’s market analysis and communication strategy are shaping the project’s direction. The team acknowledges the need to address ongoing technical challenges, particularly in AI training, and plans to coordinate closely to ensure smooth integration of new features. Everyone’s contributions were discussed, and the team remains motivated to resolve open issues.

## Weekly commitments

### Individual contribution of each participant

- **Polina**:
  - Added a quantized model (8-bit quantization) to the application. [Commit: 88834ce](https://github.com/vladkalinichencko/Killah-Prototype/commit/88834ce6517ed24588b395803f02cdeab2a002da)
  - Refactored LLM code to improve usability and maintainability for future development. [Commit: bc4ef06](https://github.com/vladkalinichencko/Killah-Prototype/commit/bc4ef0602218b5301f8af717bc1f6cddc5a12b0d)
- **Vlad**:
  - Worked on application improvements, including a settings window, a more stable and bug-free text editor, text autocomplete animation, and model loading from Hugging Face directly in the interface (work in progress, commit pending).
  - Continued training the audio modality for the AI model, encountering issues with early loss convergence and mode collapse. Replicated the approach from “An Embarrassingly Simple Approach for LLM with Strong ASR Capacity” but faced the same issue. Currently implementing and training a method from “Bridging the Modality Gap: Softly Discretizing Audio Representation for LLM-based Automatic Speech Recognition” to address modality convergence (work in progress, commit pending). Visualizations of training attempts stored in a cloud folder.
- **Zhanna**:
  - Conducted analysis and developed a strategy for marketing communications to support the project’s positioning and user engagement.

## Plan for Next Week

*No information provided for the plan for next week.*

## Confirmation of the Code’s Operability

We confirm that the code in the main branch:
- Is in working condition (not fully free of bugs yet).
- Runs on the intended platform: macOS 15 via Xcode.
If you encounter any problems running the setup, feel free to contact us for assistance. We can also provide a video demonstrating the current state of the prototype upon request.
