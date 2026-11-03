<h1 align="center">Kora</h1>

<p align="center">
  <b>AI-powered voice cooking assistant</b><br>
  Turn any YouTube recipe video or recipe photo into a step-by-step recipe, then cook hands-free with a Turkish voice assistant.
</p>

<p align="center">
  Flutter · .NET 8 · Python · Azure &nbsp;|&nbsp; <i>Currently in Google Play closed testing</i>
</p>

<p align="center">
  <img src="kora-demo.gif" width="300" alt="Kora demo: importing a recipe from YouTube and cooking with the voice assistant">
</p>

---

## Features

- **Import from YouTube** – Share a recipe video to Kora; AI extracts ingredients and steps as a structured recipe.
- **Import from photos** – Scan a handwritten or printed recipe with the camera or pick it from the gallery.
- **AI-generated recipe images** – Every imported recipe gets a cover image.
- **Hands-free cooking mode** – Say *"Selam Defne"* and move through steps by voice. The assistant reads steps aloud and answers questions in real time.
- **Offline wake word** – Wake word detection runs on the device, without internet.
- **Recipe library** – Search, filter and save favorites.

## Screenshots

| Home | My recipes | Recipe detail | Cooking mode |
|:---:|:---:|:---:|:---:|
| <img src="screenshots/01-home.jpg" width="190"> | <img src="screenshots/02-recipes.jpg" width="190"> | <img src="screenshots/03-detail.jpg" width="190"> | <img src="screenshots/04-cooking.jpg" width="190"> |

| Import from YouTube | Import from photo | Settings |
|:---:|:---:|:---:|
| <img src="screenshots/05-youtube.jpg" width="190"> | <img src="screenshots/06-photo.jpg" width="190"> | <img src="screenshots/07-settings.jpg" width="190"> |

## Tech stack

| Layer | Technologies |
|---|---|
| **Mobile** | Flutter, Dart, BLoC/Cubit, Dio, go_router, get_it/injectable, dartz, flutter_secure_storage, Vosk (on-device wake word), LiveKit client |
| **Backend** | ASP.NET Core 8 Web API, Entity Framework Core, SQL Server, ASP.NET Identity, JWT, Google Sign-In, Swagger |
| **AI** | Google Gemini (recipe extraction from video and photos, image generation), OpenAI GPT-4o-mini |
| **Voice agent** | Python, LiveKit Agents, Deepgram (speech-to-text), ElevenLabs (text-to-speech) |
| **Cloud** | Azure App Service, Azure Blob Storage, Docker |

## Architecture

- **Mobile:** Feature-based Clean Architecture (data / domain / presentation) with BLoC/Cubit for state management and the Either pattern for error handling.
- **Backend:** Layered ASP.NET Core API (API, Business, Core, Infrastructure) with Repository Pattern and Dependency Injection.
- **AI resilience:** Gemini calls use a primary → fallback model chain and retry only on transient errors, so imports keep working during provider outages.
- **Voice:** A Python agent on LiveKit handles real-time speech in Turkish, including text normalization for natural pronunciation of units and fractions.

## Source code

The source code is private because Kora is a product in active development. It can be shared with recruiters and interviewers on request.

## Contact

**Ceyda Palancı** · Flutter Developer
[LinkedIn](https://www.linkedin.com/in/ceyda-palanci-748b8b258/) · ceydapalanci08@gmail.com
