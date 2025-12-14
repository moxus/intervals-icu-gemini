# Intervals.icu Gemini Extension

This extension integrates [Intervals.icu](https://intervals.icu) with the Gemini CLI, allowing you to interact with your fitness data, create workouts, and more directly from your terminal.

## Installation

To install the extension, run the following command in your terminal:

```bash
gemini extension install https://github.com/moxus/intervals-icu-gemini
```

### Finding your Credentials
- **API Key**: Go to **Settings > API** on Intervals.icu to generate an API key.
- **Athlete ID**: Your Athlete ID is the number in the URL when you view your calendar or activities (e.g., `https://intervals.icu/athlete/12345`).

## Verification

To verify that the extension is installed correctly and connected to your Intervals.icu account, use the `/verify` slash command:

```bash
/verify
```

This command will attempt to fetch your athlete profile. If successful, it will display your Athlete ID, Name, and Timezone.
