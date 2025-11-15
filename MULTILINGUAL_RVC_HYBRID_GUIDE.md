# Supplemental Guide: Multilingual Synthesis via RVC Hybrid

This document outlines the official roadmap for adapting Alizarin Engine voices for multilingual use *before* native, from-scratch engine support is complete.

This hybrid method combines the unique, synthetic timbre from the **Alizarin Engine** with the linguistic performance of a native **Voice Actor (VA)**, using **RVC (Retrieval-based Voice Conversion)** as the bridge.

This guide serves two purposes:
1.  To document the "proof of concept" process as we apply it to our flagship **Alizarin Engine Voice**.
2.  To provide a workflow for users to create voicebanks in languages not yet natively supported by the engine.

---

## 1. The "Alizarin Engine Voice" as Proof of Concept

To ensure this workflow is robust, we will be pioneering the process with our own **Alizarin Engine Voice**.

Our goal is to create a series of high-quality, multilingual **UTAU** and **DiffSinger** voice models.

### Our Internal Workflow:
1.  **Timbre Generation:** We will generate a comprehensive, high-quality dataset using the Alizarin Engine's English voice.
2.  **Timbre Model Training:** We will fine-tune a master RVC v2 model on this dataset. This creates the definitive `Alizarin_Engine_Voice.pth` timbre model.
3.  **Performance Acquisition:** We will commission native VAs to record full, high-quality UTAU (e.g., Japanese VCV, Spanish CV) and DiffSinger (e.g., `.wav` sets) voicebanks.
4.  **Hybrid Conversion:** We will run the *entire* native VA voicebank dataset through our RVC timbre model.
5.  **Packaging & Release:** The resulting AI-converted `.wav` files will be packaged into new UTAU and DiffSinger voicebanks, possessing the Alizarin Engine's timbre but the native VA's flawless pronunciation.

As we develop this process, we will document our findings and release any tools or scripts we build (e.g., for batch processing, post-production) to the community.

---

## 2. User Workflow for Unsupported Languages

This hybrid method is the official, recommended path for any user wishing to create a voicebank in a language the Alizarin Engine does not yet natively support.

### Step-by-Step Process

**1. Step 1: Create Your Voice (Timbre)**
Use the Alizarin Engine tools to design, tweak, and generate 15-30 minutes of clean, varied audio for *your* unique voice. This is your vocal "fingerprint."

**2. Step 2: Train Your RVC Model (Timbre)**
Use this dataset to fine-tune your own RVC model (e.g., `MyVoice.pth`). This is your personal "timbre" model.

**3. Step 3: Generate a Performance (Input)**
To make your voice speak or sing, you need an "input" audio file. This file provides the **performance** (accent, emotion, pitch, and pronunciation).

### How to Get High-Quality "Performance" Inputs

This is the most critical step for making your voice sound unique and high-quality. You **must** ensure you have the legal and ethical rights to use the audio for this purpose.

> **Warning: The "One-Size-Fits-All" Problem**
> We do *not* provide "default" language audio files. Using a single "default" file would make every voice on our platform sound identical, with the same robotic performance. Our goal is to maximize your creative freedom.

Here are the recommended ways to get a unique performance:

* **Collaborate (Safest & Best Option):** Find a voice actor to provide a unique performance just for you. This is the best way to get custom, high-quality results. (See **Section 5. The Alizarin Hub** for details on how to connect with VAs).
* **Record Your Own Audio:** If you are a native speaker of the target language, this is a perfect, direct option.
* **Use Open-Source UTAU Banks (With Extreme Caution):** This is a powerful method, but it **requires a critical legal and ethical check.**
    1.  **Find a Voicebank:** Locate a UTAU voicebank for your target language.
    2.  **CHECK THE TERMS OF USE (TOU):** This is the most important step. Find the `readme.txt` or website for the bank.
    3.  **Look for Permission:** You must find a bank that **explicitly allows** use for AI, RVC, or "voice conversion." If the TOU forbids AI use, or is unclear, **you must not use it without getting permission from the VA and creation team that owns it.**
    4.  **Wait for "Yes":** Not getting a response or finding a voicebank that is no longer supported **DOES NOT** give you the okay to use that voice. Until you get an explicit "yes," assume the answer is "no."
    5.  **Render Your Input:** Once you have a permitted bank, you can find a `.ust` (song file), render the vocals, and safely use that `input.wav` for your RVC model.

---

## 3. Key Challenge: Preserving Vocal Identity

A common problem with RVC conversion is "timbre bleed" (where the VA's voice leaks through) or the introduction of artifacts. Preserving the *exact* synthetic character of your Alizarin voice is our top priority.

Our development of the Alizarin Engine Voice packs will focus on solving this. We will test and document:
* **Optimal Dataset Size:** The effect of using 10 min vs. 30 min+ of source data for the timbre model.
* **RVC Training Settings:** The best practices for epochs, batch size, and model types to maximize timbre preservation.
* **Input vs. Timbre Matching:** Techniques to ensure the conversion is as stable as possible, even when the input VA's pitch or tone is different from the source.

The findings from this research will be published as a "Best Practices" guide for all Alizarin Engine users.

---

## 4. Expanding Support for Unique & Niche Languages

This hybrid workflow's greatest strength is its flexibility. It allows for the creation of voicebanks for languages the Alizarin Engine may *never* natively support.

### How RVC and UTAU Enable This
The RVC model (your timbre) is **language-agnostic**. It only converts vocal texture.
The UTAU platform is also **language-agnostic**. It only plays `.wav` files mapped in an `oto.ini`.

This means **you can create a voicebank for *any* language that has a defined UTAU phonetic reclist.**

From a single English Alizarin Engine voice, you can partner with a VA to create banks for:
* **Major Languages:** Japanese (CV, VCV), Korean (VCCV), Spanish (CV), Mandarin (CVVC).
* **Niche Languages:** Any language where a community member has built a reclist (e.g., French, Portuguese, Tagalog, etc.).
* **Custom Systems:** Even unique languages or conlangs, so long as you (or your VA) can record the necessary audio snippets and map them in an `oto.ini`.

This workflow empowers users to bring their synthetic voices to any linguistic community they choose, far beyond the scope of our initial native engine support.

---

## 5. The Alizarin Hub: A Collaboration Space

To facilitate this workflow, we have a **dedicated channel** for voice development in our official Alizarin Engine Discord community.

This is the best place for "Timbre Creators" (Alizarin users) and "Performance Providers" (VAs) to connect and collaborate.

### Join the AlGlow Den:
* **Discord:** [Join the Alizarin Engine Discord!](https://discord.gg/6c4yTrMqRt)
* **Collaboration Channel:** Look for the `#va-collab` channel (or a similar name) to find a partner or offer your services.

This hub is designed to be a marketplace for:
* **Timbre Creators:** Users who have built a unique voice with the Alizarin Engine.
* **Performance Providers:** Voice actors willing to be commissioned to record voicebank data.

---

## 6. The Long-Term Vision: Native Engine Support

The RVC hybrid workflow detailed on this page is the current, most effective, and high-quality method for multilingual support.

Our ultimate, long-term goal is to integrate full, native multilingual support *directly into the Alizarin Engine*, allowing for synthetic generation in other languages from scratch. This is a massive R&D challenge.

By providing this hybrid workflow, we empower the community to expand language support *now*. The success and adoption of this method will help grow the community, and in turn, help fuel the long-term development of native engine support.

---

## 7. Ethical Code of Conduct & RVC Use Addendum

This Code of Conduct is a mandatory addendum to the Alizarin Engine `USAGE_GUIDE.md`.

Our main `USAGE_GUIDE.md` (Section 2.3) **prohibits** using Alizarin Engine output for any AI model training by default. This document grants a **conditional exception** *only* for the RVC-hybrid workflow detailed here, and this permission is contingent on your strict and total adherence to the rules below.

These rules apply *regardless* of the tool used (e.g., potential future built-in engine tools or your own external RVC software). If any Alizarin Engine asset (a voice you created, or one of our official voices) is used in the workflow, these terms are in effect.

### 7.1. Core Principles

* **1. Respect the "Performance" (The VA):**
    * **No Unclear Contracts:** When commissioning a Voice Actor (VA), you **must** have a clear, written contract that states *exactly* what the audio will be used for (e.g., "to serve as an input for RVC/AI voice conversion to create a new, hybrid voicebank").
    * **Respect Distribution Rights:** Your contract must also specify whether you have the right to publicly distribute the final, converted voicebank.

* **2. Respect the "Timbre" (The Voice Source):**
    * **No Stealing:** You may **not** create an RVC model from any voice source without that creator's explicit, written permission.
    * **This includes (but is not limited to):**
        * Other Alizarin Engine users' voices.
        * Our official Alizarin Engine Voice(s).
        * Other VTubers or content creators.
        * Celebrities or public figures.
        * Commercial voicebanks (Vocaloid, Synthesizer V, etc.).
    * The only voice you can train an RVC model on is one you have **created yourself** or one you have **explicit, written permission** to use.

* **3. Respect the Community (No Malicious Use):**
    * **No Hate or Harm:** You may not use the Alizarin Engine or any voicebanks created with it for harassment, hate speech, defamation, or any illegal or harmful content.
    * **Clear Attribution:** We highly recommend clear attribution for all parties. A "readme" for your bank should state:
        * "Timbre created with Alizarin Engine by [Your Name]"
        * "Performance provided by [VA's Name / Credits]"

### 7.2. Breach of Conduct

Failure to abide by any of the terms in this section is a direct breach of the `USAGE_GUIDE.md` and this addendum.

1.  This breach **immediately and automatically revokes** the conditional permission for AI use granted by this document. Any further AI conversion will be considered a willful violation of the `USAGE_GUIDE.md` (Section 2.3).
2.  Furthermore, this breach will result in:
    * An **immediate ban** from all Alizarin community spaces.
    * An **automatic revocation** of your license (EULA) for all official Alizarin Engine Voices.
    * A **termination of your right to use the Alizarin Engine for any commercial purpose**, as per Section 3.1 of the `USAGE_GUIDE.md`.

While we cannot legally enforce these terms if you use external tools *without* leveraging any Alizarin Engine assets, we strongly urge the entire community to adopt these ethical principles.

---

## 8. Frequently Asked Questions (FAQ)

**Q: What if I want to convert a voice someone else made with the Alizarin Engine into another language?**
**A:** **No, not without their explicit permission.** Attempting to do this without the original creator's knowledge and consent is "timbre theft" and a violation of our Code of Conduct (Section 7.1).

The only person who has the right to authorize an RVC model of a voice is the **original creator**. If you want to use *their* specific voice, you must:
1.  Contact them directly.
2.  Get their explicit, written permission.
3.  Follow any guidelines or collaboration terms they set.

If you cannot get permission, you must make your *own* Alizarin voice and follow the RVC hybrid workflow yourself.

**Q: Can I use the official "Alizarin Engine Voice" to make my own RVC conversions?**
**A:** **Not independently.** Attempting to do this on your own is considered "timbre theft" (Section 7.1) and is a violation of our terms. The Alizarin Engine Voice is our flagship product, and we must maintain a high standard of quality.

However, we are open to **official collaborations** to expand the Alizarin Engine Voice into new languages. If you are a VA or producer who wishes to propose an official language conversion, please contact us via the **"Special Requests" form** (as detailed in our `USAGE_GUIDE.md`). All official collaborations must be done with our direct involvement, approval, and adherence to our quality standards.

**Q: What if I can't find or afford a VA for my target language?**
**A:** We understand this challenge. However, the solution is **not** to use a voicebank without permission (a violation of Section 2.3). Your best options are:
1.  Check the `#va-collab` channel on our Discord for VAs who may be willing to trade their services for a custom voice.
2.  Search for UTAU banks that have an *explicitly permissive* TOU that allows AI use (as detailed in Section 2).
3.  Be patient and save up. A high-quality, ethically-sourced voice is worth the wait and protects everyone.

**Q: Why does my converted voice sound strange, like it has an accent?**
**A:** This workflow (RVC) does not teach your voice *how* to speak a new language; it only copies the *timbre*. Your voice will only sound as good as the **input "performance"** you provide. If your input audio is from a non-native speaker (or a different UTAU system), you will get a non-native or "accented" result. The RVC model (your timbre) and the input audio (the performance) must both be high-quality.
