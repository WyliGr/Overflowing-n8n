# 🎬 All8cine

> Stop checking dozen of theater websites. Let automation bring the showtimes to you.

**All8cine** is an [n8n](https://n8n.io/) workflow template designed to make the cinema-going experience frictionless. It scrapes screening data via the Allociné API and delivers a curated schedule directly to your **Discord** every morning.

---

## 🚀 Features

* **Centralized Data:** Aggregates screenings from multiple theaters into one view.
* **Daily Updates:** Automatically pushes the latest schedules to Discord.
* **Zero Friction:** No more manual searching or navigating cluttered theater websites.
* **Extensible:** Built on n8n, so you can easily swap Discord for Telegram, Slack, or Email.

## 🛠️ How it Works

1. **Fetch:** The workflow queries the **Allociné API** for specific theaters in your area.
2. **Process:** It filters and formats the raw JSON data into a human-readable summary.
3. **Notify:** The final digest is sent via a **Discord Bot** to your preferred channel.

## 📦 Setup

1. **Import:** Download the `template.json` or the `strasbourg.json` and import it into your n8n instance.
2. **Configure:** * Update the **Theater IDs** in the initial node to match your local cinemas.
3. Add your **Discord Bot Token**.
4. **Schedule:** Set the Schedule node to your preferred time (e.g., 8:00 AM).

## 🥨 Strasbourg

I have a pre-configured workflow for the city of strasbourg (*Tarte flambées, marché de Noël, Cathédrale tout ça ...*). It comes with the **Vox** theater, the **Cosmos** Theater and the **UGC Ciné Cité Rivétoile**.
Soon I'll add the **Stars** theater