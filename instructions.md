# Intervals.icu MCP Server Instructions

This document provides instructions for using the `@moxus/intervals-mcp` server, including available tools, API usage, unit conversions, and workout builder syntax.

## Available Tools

The following tools are available for interacting with Intervals.icu:

### Activities
- **`getActivities`**: Retrieve a list of activities.
- **`getActivityDetails`**: Get detailed information for a specific activity.
- **`get_activity_intervals`**: Get detailed interval information for an activity.

### Events (Workouts)
- **`createEvent`**: Schedule a new workout or event.
- **`createBulkEvents`**: Schedule multiple events at once.
- **`getEvents`**: Retrieve planned workouts and events.
- **`deleteEvent`**: Remove a specific event.
- **`deleteBulkEvents`**: Remove multiple events.

### Athlete & Wellness
- **`getAthleteDetails`**: Retrieve athlete statistics and settings.
- **`getWellnessData`**: Fetch wellness data (sleep, stress, recovery).

## API Usage

For detailed information on the data structures and API endpoints used by these tools, refer to the [Intervals.icu API Documentation](https://intervals.icu/api-docs.html#get-/api/v1/athlete/-id-/events/-eventId-).

## Unit Conversions

Intervals.icu often uses meters per second (m/s) for speed. Here is how to convert to common pace units:

### m/s to min/km
Formula: `1000 / (speed_in_m_s * 60)` or `16.6666... / speed_in_m_s`

**Example:**
- Speed: 3.33 m/s
- Calculation: `1000 / (3.33 * 60) = 5.00`
- Result: **5:00 min/km**

### m/s to min/mile
Formula: `1609.34 / (speed_in_m_s * 60)` or `26.822... / speed_in_m_s`

**Example:**
- Speed: 3.33 m/s
- Calculation: `1609.34 / (3.33 * 60) ≈ 8.05`
- Result: **8:03 min/mile** (0.05 * 60 = 3 seconds)

## Workout Builder Syntax

When creating workouts or workout events (e.g., using `createEvent`), the `description` field uses the Intervals.icu builder syntax.

**Important for Repeating Steps:**
To create repeating intervals (e.g., 5x 3m hard, 3m easy), you **must** separate the repeating block with empty lines.

**Example:**

```text
- 15m Z2 Warmup

5x
- 3m Z5 VO2 Max
- 3m Z1 Recovery

- 10m Z1 Cooldown
```

Without the empty lines, the parser may not correctly identify the nested structure.

For more details, see the [Workout Builder Documentation](https://github.com/moxus/intervals-icu-mcp-ts/blob/main/workout_doc.md).
