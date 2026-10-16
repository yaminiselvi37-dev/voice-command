# Voice-Controlled Smart Home Automation 🏠🔊

A simple Python-based prototype that combines machine learning text processing and browser-based speech recognition to control smart home appliances (like a fan and a light) using voice commands.

Built inside a [Google Colab](https://colab.research.google.com/drive/1cbU95f7oYBddvV_dfSWOxj8WfxrUeDe1#scrollTo=l7kxwP7M18Ll) environment, this project demonstrates how to capture microphone audio directly from the browser, process it using speech recognition, and classify user intent using a Naive Bayes text classification pipeline.

---

## Features

* **Browser Audio Recording:** Uses JavaScript within Google Colab to record 5 seconds of audio directly from your microphone.
* **Speech-to-Text:** Converts recorded voice clips into text using Google's Speech Recognition API (`SpeechRecognition`).
* **Intent Classification:** Employs a Scikit-Learn `Pipeline` combining `TfidfVectorizer` and a `MultinomialNB` (Multinomial Naive Bayes) classifier to understand and map various natural language commands to specific appliance actions.
* **Smart Home State Management:** Tracks and updates the state of devices (e.g., `fan` and `light`) and prints out the system status.

---

## Prerequisites & Dependencies

The project requires the following Python libraries, which are automatically installed via `pip`:

* `scikit-learn`
* `SpeechRecognition`
* `pydub`

You can install them locally using:
```bash
pip install scikit-learn SpeechRecognition pydub

```

---

## Code Overview

1. **Training the Intent Classifier:**
The model is trained on a predefined list of text commands (e.g., *"turn on fan"*, *"switch off light"*, *"turn on everything"*) mapped to corresponding labels (`fan_on`, `light_off`, `all_on`, etc.).
2. **Voice Recording Function (`record_voice`):**
Executes a JavaScript snippet via IPython Display to capture an audio stream from the browser's microphone, converts the audio into a WAV buffer, and processes it.
3. **Appliance Controller (`control_appliances`):**
Parses the recognized speech string, evaluates keywords (such as `fan`, `light`, `on`, `off`, `all`), updates appliance states, and displays the current smart home status.

---

## Example Usage

Run the main execution function in your Python environment or notebook:

```python
run_voice_command()

```

* **Sample Output:**
```text
Speak within the next 5 seconds...
Recording... Speak your command now.
Recording complete.
Recognized voice: turn on light

--- SMART HOME STATUS ---
Fan: OFF
Light: ON

```



---

## License

This project is open-source and available for educational and experimentation purposes.

```

```
