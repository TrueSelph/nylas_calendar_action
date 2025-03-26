# Nylas Calendar Action

![GitHub release (latest by date)](https://img.shields.io/github/v/release/TrueSelph/nylas_calendar_action)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/TrueSelph/nylas_calendar_action/test-action.yaml)
![GitHub issues](https://img.shields.io/github/issues/TrueSelph/nylas_calendar_action)
![GitHub pull requests](https://img.shields.io/github/issues-pr/nylas_calendar_action)
![GitHub](https://img.shields.io/github/license/TrueSelph/nylas_calendar_action)

JIVAS action wrapper for interfacing with the Nylas API for calendar management.

## Package Information

- **Name:** `jivas/nylas_calendar_action`
- **Author:** [V75 Inc.](https://v75inc.com/)
- **Architype:** `NylasCalendarAction`
- **Version:** `0.0.1`

## Meta Information

- **Title:** Nylas Calendar Action
- **Group:** core
- **Type:** action

## Configuration

- **Singleton:** true

## Dependencies

- **Jivas:** `^2.0.0`
- **Pip:**
  - `pytz`
  - `requests`

This package, developed by V75 Inc., provides a JIVAS action wrapper for the Nylas API, enabling seamless calendar management and scheduling. As a core action, it simplifies interactions with calendar data. The package is a singleton and requires the Jivas library version 2.0.0.

---

## How to Use

Below is detailed guidance on how to configure and use the Nylas Calendar Action.

### Overview

The Nylas Calendar Action provides an abstraction layer for interacting with the Nylas API. It supports multiple functionalities, including:

- **Fetching available times** for scheduling.
- **Creating calendar events** with participants.
- **Deleting events** from calendars.
- **Retrieving event details**.

---

### Configuration Structure

The configuration consists of the following components:

### `open_hours`

Defines the default open hours for availability checks.

```python
open_hours = [
    {
        "days": [1, 2, 3, 4, 5],  # Monday to Friday
        "timezone": "America/Guyana",
        "start": "8:00",
        "end": "16:30"
    },
    {
        "days": [6],  # Saturday
        "timezone": "America/Guyana",
        "start": "9:00",
        "end": "14:00"
    }
]
```

---

### Example Usage

### Fetch Available Times

```python
available_times = nylas_calendar_action.get_available_times(
    start_time="2023-10-01 08:00:00",
    base_url="https://api.nylas.com",
    duration=30,
    cal_email="user@example.com",
    calendar_id="calendar123",
    bearer_token="Bearer your_token"
)
```

### Create an Event

```python
event = nylas_calendar_action.create_event(
    start_time="2023-10-01 10:00:00",
    grant_url="https://api.nylas.com",
    duration=60,
    purpose="Team Meeting",
    calendar_id="calendar123",
    user_name="John Doe",
    email="john.doe@example.com",
    bearer_token="Bearer your_token"
)
```

### Delete an Event

```python
response = nylas_calendar_action.delete_event(
    grant_url="https://api.nylas.com",
    calendar_id="calendar123",
    event_id="event456",
    bearer_token="Bearer your_token"
)
```

---

## 🔰 Contributing

- **🐛 [Report Issues](https://github.com/TrueSelph/nylas_calendar_action/issues)**: Submit bugs found or log feature requests for the `nylas_calendar_action` project.
- **💡 [Submit Pull Requests](https://github.com/TrueSelph/nylas_calendar_action/blob/main/CONTRIBUTING.md)**: Review open PRs, and submit your own PRs.

<details closed>
<summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a git client.
   ```sh
   git clone https://github.com/TrueSelph/nylas_calendar_action
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.
8. **Review**: Once your PR is reviewed and approved, it will be merged into the main branch. Congratulations on your contribution!
</details>

<details open>
<summary>Contributor Graph</summary>
<br>
<p align="left">
    <a href="https://github.com/TrueSelph/nylas_calendar_action/graphs/contributors">
        <img src="https://contrib.rocks/image?repo=TrueSelph/nylas_calendar_action" />
   </a>
</p>
</details>

## 🎗 License

This project is protected under the Apache License 2.0. See [LICENSE](../LICENSE) for more information.