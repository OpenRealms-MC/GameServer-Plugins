# Gameserver-Plugins

This repository is dedicated to managing all external plugins for the main gameserver. It ensures that the server setup remains consistent and automated across all developers and deployments.

---

> **⚠️ WARNING: Project Under Development**
> This project structure is currently in active development. While we strive for consistency, some features or scripts may not be fully functional yet. We appreciate your patience and welcome any contributions to help us improve the system.

---

This repository **does not contain any plugin JAR files directly**. Instead, it contains two files that our setup script uses to fetch the plugins:

- `plugins-repos.txt`
- `plugins-downloads.txt`

### `plugins-repos.txt`

This file is for **open-source plugins hosted on GitHub**. Each line should be the URL of a GitHub repository for a plugin.

When the setup script runs, it will automatically clone each of these repositories, compile the plugin's code, and move the resulting `.jar` file into the server's `plugins` folder.

**Example:**
```

[https://github.com/PlaceholderMC/MyOpenSourcePlugin](https://github.com/PlaceholderMC/MyOpenSourcePlugin)
[https://github.com/AnotherDev/EssentialPlugin](https://github.com/AnotherDev/EssentialPlugin)

```

---

### `plugins-downloads.txt`

This file is for **external plugins that are not open-source or are hosted elsewhere**. Each line should be a direct download link to a `.jar` file.

The setup script will use `wget` to automatically download each of these files and place them directly into the server's `plugins` folder.

**Example:**
```

[https://example.com/downloads/MyPremiumPlugin.jar](https://example.com/downloads/MyPremiumPlugin.jar)
[https://another-site.net/releases/SomePlugin.jar](https://another-site.net/releases/SomePlugin.jar)

```

By following this structure, our project remains clean and organized, while ensuring that all necessary plugins are installed automatically during the setup process.
