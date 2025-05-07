# meowdiner-support
Technical support docs for the MeowDiner Unity2D game—FAQs, troubleshooting tips and contact info for players.
# MeowDiner Technical Support

Welcome to the official support repository for **MeowDiner**, the cute casual tap‑and‑catch Unity2D game for iOS and Android. Here you’ll find solutions to common issues, troubleshooting tips, and contact information.

---

## 📋 Table of Contents

- [Frequently Asked Questions](#frequently-asked-questions)  
- [Troubleshooting Guide](#troubleshooting-guide)  
- [Reporting Bugs](#reporting-bugs)  
- [Contact Us](#contact-us)  

---

## ❓ Frequently Asked Questions

### Q: The fish aren’t spawning or moving.  
**A:**  
1. Make sure you have assigned all **Spawn Points** under the `FishSpawner` component in the Inspector.  
2. Verify that your **Fish Prefabs** list is populated and none of the entries are `None`.  
3. Check your scene’s **Build Settings**: both `startscene` and `gamescene` must be added under **Scenes In Build**.

### Q: Clicking the Restart or Back buttons has no effect.  
**A:**  
- Confirm your **GameManager** is not paused (`Time.timeScale == 0`).  
- In your Button’s **On Click()** list, ensure the correct function (`Restart()` or `BackToMenu()`) is bound to the right game object.  
- Verify that the target scene names exactly match those in **SceneManager.LoadScene("…")**.

### Q: My custom UI layout looks correct in the Editor but is stretched or misaligned at runtime.  
**A:**  
- Add a **Canvas Scaler** component on your Canvas and set **UI Scale Mode** → **Scale With Screen Size**.  
- Use **Reference Resolution** (e.g. 1080×1920) and **Match** = 1 (for portrait).  
- Anchor your `BoardPanel` or other panels to Center rather than Stretch.

---

## 🛠 Troubleshooting Guide

1. **MissingReferenceException**  
   - Indicates a `public` field in your script lost its Inspector binding. Re‑drag the missing prefab or transform back into the slot.  
2. **ArgumentOutOfRangeException**  
   - Means a `List` index is invalid. Check your spawn range logic and ensure your collections (`spawnPoints`, `fishPrefabs`, etc.) are non‑empty.  
3. **NullReferenceException on Start()**  
   - Often caused by calling `Instantiate()` on a `null` prefab or accessing a component that isn’t assigned. Use `Debug.Log()` to verify your fields before use.

---

## 🐞 Reporting Bugs

If you encounter an issue that isn’t covered above:

1. Open a new **Issue** on this GitHub repo.  
2. Describe the problem and steps to reproduce.  
3. Include screenshots or console logs if possible.

---

## ✉️ Contact Us

If your question isn’t answered here, feel free to reach out:

- **Email:** muzi329339@gmail.com  

We aim to respond within 48 hours. Happy feeding!  

---
