# Anti-Gravity Interactive Experience 🌌

A modern, lightweight, single-page zero-gravity simulation built with vanilla HTML5, CSS3, JavaScript, and connected with **Supabase** for persistent cloud cards and telemetry.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)
![Supabase](https://img.shields.io/badge/Supabase-Integrated-3ECF8E.svg)

## ✨ Features

- **Microgravity & Inertia**: Floating glassmorphic cards and ethereal quantum orbs that drift smoothly with harmonic wave forces.
- **Physics-Based Cursor Interaction**:
  - **Repulsion & Attraction**: Switch between repulsive or attractive gravitational fields that react dynamically based on distance.
  - **Momentum Transfer**: Fast mouse movements impart kinetic impulse and spin to nearby objects.
  - **Grab & Fling**: Click and drag any item to throw it across the viewport with physics-based inertia.
  - **Anti-G Shockwave Pulse**: Click anywhere (or hit <kbd>Space</kbd>) to release a gravitational ripple wave.
- **Supabase Cloud Sync**:
  - Launch custom floating cards into zero gravity and persist them in your Supabase database.
  - Automatically loads cloud cards on startup across all client sessions.
  - In-app configuration modal to enter your Project URL and Anon API key.
- **Ultra Clean & Modern UI**:
  - Glassmorphic telemetry displays with real-time HUD stats (FPS, active entities, field mode).
  - Ambient starfield and dynamic gravitational glow around the cursor.

---

## ⚡ Supabase Setup

To persist cards and telemetry in your own Supabase project:

1. Create a project at [supabase.com](https://supabase.com).
2. Open the **SQL Editor** in your Supabase dashboard and run:

```sql
create table if not exists cosmic_cards (
  id serial primary key,
  title text not null,
  body text not null,
  metric text default '0.00g',
  tag text default 'Supabase',
  created_at timestamp with time zone default timezone('utc'::text, now()) not null
);

-- Enable RLS and grant public read/write access
alter table cosmic_cards enable row level security;
create policy "Allow public read" on cosmic_cards for select using (true);
create policy "Allow public insert" on cosmic_cards for insert with check (true);
```

3. Open the app, click **"Supabase Uplink"** in the top left header, and paste your **Project URL** and **Anon Key**.
4. Click **+ Cloud Card** to launch new zero-gravity cards that sync in real-time!

---

## 🚀 Deployment on Vercel

1. Import this repository into [Vercel](https://vercel.com/new).
2. Framework Preset: **Other / Static**.
3. Deploy!
