# Drupal Configuration Sync Guide

To ensure consistency between development environments, we use **Drupal Configuration Management** via the `config/sync` directory. This allows us to version-control all configuration changes—such as content types, fields, roles, and languages—and keep both developer environments in sync.

## 🚀 Workflow

### 1. Making Configuration Changes

One developer makes changes through the Drupal Admin UI, such as:

- Creating or editing content types
- Adding fields
- Setting up roles and permissions
- Configuring languages

Then exports the updated configuration with:

```bash
ddev drush config:export
# or the shorthand
ddev drush cex
```

This updates the files in the `config/sync` directory.

✅ **Next step:** Commit and push these changes to the Git repository.

---

### 2. Syncing Configuration on Another Environment

The other team member pulls the latest changes from Git and imports the configuration into their local Drupal instance:

```bash
ddev drush config:import
# or the shorthand
ddev drush cim
```

This applies all new settings locally, keeping environments in sync.

---

### 3. Checking for Differences (Optional)

Before importing, you can check for configuration differences:

```bash
ddev drush config:status
```

---

## ✅ Benefits

- 🔁 No need to share database dumps  
- 📁 Clean, version-controlled workflow  
- 🤝 Easier collaboration  
- 📐 Follows Drupal best practices  

---

> Tip: Always run `drush config:status` before importing, especially when collaborating on multiple config-related features.
