# camelCase™

**Eliminates the silence between notes — or keeps only the silence.**

A [Loopy Pro forum](https://forum.loopypro.com/) joke that turned out to be real, working DSP. Runs entirely in your browser. Nothing uploads.

> *More notes. No gaps. Maximum music. Because time is a flat circle, and we flattened it.*

-----

## The story

It started as a parody ad on the Loopy Pro forum: a fake AUv3 effect called **camelCase** that “eliminates the silence between notes so your music can be up to 100× faster to listen to.” Techno at 1200 BPM. John Cage’s 4′33″ now at 0′00″. Just a weekly $9.99 subscription.

Then someone made it real. This is that — a functioning, single-file web app. No subscription. No AUv3 (sorry). Just the bit, fully operational.

## What it actually does

Under the joke is a legitimate operation: **silence-gated time compression.** It scans the audio in short frames, measures the peak level against a threshold (the **SILENCE** knob), and splices out everything below it — with a 5 ms pre-onset guard and an 80 ms release hold so note attacks and tails survive, plus short edge crossfades so the cuts don’t click. The “100× faster” claim becomes a live, measured readout: original duration → compressed duration → actual multiplier.

It’s genuinely useful for **speech, not music** — the joke only lands because removing musical rests destroys the music. Pointed at a podcast, lecture, or voice memo, it’s a dead-air trimmer (the same idea behind tools like Descript or “strip silence” in a DAW). Its one real edge: it’s **100% local** — your audio never leaves the device.

## Two modes

- **⚡ Eliminate silence** — keep the notes, drop the gaps. The original gag.
- **🤫 Keep only silence** — the inverse: drop the notes, keep the gaps. On a real recording this isn’t pure digital silence — it’s the breaths and room tone *between* phrases, concatenated. That’s an actual room-tone / noise-profile extract you can load into a sampler.

## Features

- Drop in an audio file, or **record live** from the mic
- The **SILENCE** knob sets the threshold (gentle → aggressive)
- Live before/after waveforms and stats
- Play original vs. processed
- Export the result as a `.wav`
- Fully client-side — no server, no upload, no tracking

## Use it

It’s one self-contained HTML file. Either:

- **Visit the live version:** *[add your GitHub Pages URL here]*
- **Or run it locally:** download `index.html` and open it in any modern browser.

### ⚠️ A note on recording

The mic only works on a **top-level page** (like the GitHub Pages link). Browsers won’t let an embedded `<iframe>` request microphone permission unless the parent page explicitly grants it — so recording will silently fail inside previews or embeds, while file-drop and both modes work everywhere. If you want live recording, use the hosted link.

## Credits

- Original parody-ad concept: **@coloringpad** and **@Fear2Stop** on the Loopy Pro forum
- Made into a working app: **@FizzyLizzy27**
- John Cage (probably): *“I wrote 4′33″ as a statement. You turned it into a speedrun. I can’t even be mad.”*

## License

*(Pick one — MIT is the usual choice for this kind of thing. Add a `LICENSE` file via GitHub’s “Add file → Create new file → LICENSE” picker.)*