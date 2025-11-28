[**◀ Back to Project Home (README.md)**](README.md) | [**ALIZARIN Voice EULA**](USAGE_GUIDE.md) | [**Third-Party Licenses**](THIRD_PARTY_LICENSES.md)
***

# ALIZARIN Engine - Creator's Guide & Best Practices

This document provides helpful advice, suggestions, and answers to common questions for creators using the **ALIZARIN Engine** (LGPLv3) to build their own unique voices.

**This is not a legal document.** The rules in this guide are suggestions, not requirements. The only legally binding document for the ALIZARIN Engine itself is the **LGPLv3 license**.

---

## I. Suggested Voicebank Usage Guidelines (Elaborated)

The `README.md` lists a set of minimum suggested guidelines. Here is a more detailed look at *why* we recommend them for your own voicebank's EULA.

### Why Have a EULA?

A "Terms of Use" or EULA (End User License Agreement) is a contract that protects your creation. It allows you to set rules for your voice and gives you the legal power to enforce them (e.g., via DMCA).

### Suggested Minimum Rules Explained

* **Commercial Music Use: Allowed**
    * **Why:** This is the #1 way to encourage adoption. Allowing producers to monetize songs gives your voice a massive audience and makes it a viable tool, not just a toy.
* **Hate Speech/Slander: Strictly Prohibited**
    * **Why:** This protects you, your character, and your community. It gives you the immediate right to demand takedown of any content that uses your voice to harass others or promote hate.
* **Impersonation/Fraud: Strictly Prohibited**
    * **Why:** As the creator of a synthetic voice, this is your core ethical responsibility. This rule explicitly forbids users from using your voice to commit fraud or deepfake-style impersonation.
* **Voice Redistribution: Prohibited**
    * **Why:** This is your most important IP protection. This rule ensures that the *only* place to get your voice is from your official download page. This forces every user to see and agree to *your* EULA, which is what makes it legally enforceable.

### Optional Rules to Consider (At Your Discretion)

* **R-18/Adult Content:** Do you want your voice used for sexually explicit content? You must state this clearly. A common "middle ground" is "Prohibited unless explicitly permitted by the creator."
* **Religious/Political Content:** Do you want your voice to be the face of a political movement or religious sermon? If not, you must prohibit it.
* **Voice Alterations/Training:** Do you want others using your voice files to train their *own* AI? Most creators prohibit this to protect their voice's unique identity from being "stolen" and re-trained.

---

## II. Suggested Character IP Guidelines (Elaborated)

Your voicebank's "character" (the name, art, and personality) is a separate piece of Intellectual Property (IP) from the voice itself. This is how major synth companies operate, and it's a model we highly recommend.

By separating your "Voice EULA" (which should be permissive) from your "Character License" (which should be strict), you can let people freely make *music* with your voice while you maintain full control over your *brand* and *image*.

### Suggested Minimum Rules Explained

* **Commercial Character IP or Visual Art Use: Prohibited without permission.**
    * **Why:** This is your most important brand protection. This rule means someone can't just take your character's art, print it on a T-shirt or an album cover, and sell it. It requires them to get a license from you (which you can charge for), protecting your commercial rights. If you want this to be free use, you can still require they submit the **commercial** work to you for approval of the **character** and brand usage. If you don't like it, you can always veto them having rights to the character. However, this is **different** from the ability to veto voice usage. If you dislike the song or message but it does not violate the terms **associated** with your voicebank, you cannot force them to take it down; however, you *can* refuse their request to use your character's name and likeness. If they use your character anyway after you formally deny the request then, and only then, would you have grounds to issue a takedown for the song's for the basis of the visual elements.
* **Name/Identity Use: Prohibited for branding.**
    * **Why:** This prevents someone from creating a new product (like their own API, software, or even another voice) and branding it with your character's name, which would confuse the community and dilute your brand.
* **Hate Speech/Slander: Strictly Prohibited.**
    * **Why:** Just like with the voice, this rule gives you the legal right to issue a takedown if someone uses your character's *image* (e.g., in a comic or video) to promote hate, harassment, or illegal acts.
* **Derivative Art / Fan Work: Allowed.**
    * **Why:** This is crucial for community building. You *want* people to create fan art and non-commercial fan works. This rule encourages that, while all the other rules protect you from that fan art being used in a way you don't approve of (e.g., commercially or for hate speech).

---

## III. How to Protect Your IP (Creator Q&A)

* **Q: How do I enforce my rules?**
    * **A:** Your primary tool is your EULA. When someone downloads your voice, they are agreeing to your terms.
        * **For Character Art:** If someone uses your character art on merchandise, you can issue a **DMCA Takedown Notice** to the storefront (like YouTube, Spotify, or an online store) for copyright infringement.
        * **For Voice Misuse (Hate Speech, etc.):** You can issue a **DMCA Takedown** or a formal **Cease & Desist** notice for a *breach of contract* (your EULA).
* **Q: Why should I separate my Voice and Character rules?**
    * **A:** This is the "Hatsune Miku" model and is highly recommended. It gives you maximum flexibility.
        * **Voice License (EULA):** This is for the *sound*. You want this to be permissive so people can make music (e.g., "Commercial music is fine").
        * **Character License (IP):** This is for the *art and name*. You want this to be strict so you control your brand (e.g., "You must pay me to put this character on a T-shirt").
    * By separating them, you let people *use* your tool while you *control* your brand.
* **Q: How do I handle takedowns?**
    * **A:** First, always try contacting the user politely. If they refuse to comply, you can use the official "DMCA Takedown" or "Copyright Infringement" form on most platforms (YouTube, Spotify, Bandcamp, etc.). You will need to provide a link to your original work (your character art, your voice demo) and a link to the infringing content, and state that it violates your EULA/License.

---

## IV. External Tools for Voice Design

Creating a purely synthetic voice requires precise control over frequencies and textures. While the ALIZARIN Engine handles the generation, we highly recommend the following open-source tools to visualize your sound source during the design process.

> **Note:** These are standalone external applications. They are not integrated into the engine but are recommended for your workflow.

* **[Friture](https://friture.org/)** (GPLv3): Recommended for **real-time verification**. Use this to see your formant peaks and noise textures live while you tweak parameters.
* **[Sonic Visualiser](https://www.sonicvisualiser.org/)** (GPLv2): Recommended for **offline analysis**. Use this to inspect your generated `.wav` samples for alignment errors or unwanted frequency artifacts.

### Real-Time Audio Monitoring (The "Air-Gap" Method)

To monitor your synthetic source in real-time with an analyzer like Friture, you can route the engine's audio output to a virtual input. This allows you to "see" the voice without needing to integrate complex analysis code.

1. **Install a Virtual Cable:**
    * **Windows:** [VB-Cable](https://vb-audio.com/Cable/)
    * **macOS:** [BlackHole](https://github.com/ExistentialAudio/BlackHole)
    * **Linux:** Use PulseAudio/PipeWire sinks.
2. **Route the Engine:** In your generation script, set the audio output device to the Virtual Cable Input.
3. **Route the Analyzer:** In Friture, set the **Input Device** to the Virtual Cable Output.
4. **Result:** When you run the engine, the audio will visualize instantly in Friture.
