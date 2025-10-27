Inkhale — Shared Dashboard (Supabase)
=====================================
This version lets everyone see the same data by saving to Supabase.

Setup:
1) Create a Supabase project
2) SQL Editor → run:

create table if not exists public.sales (
  id bigserial primary key,
  org_id text not null,
  date date not null,
  amount numeric not null,
  note text
);
create table if not exists public.expenses (
  id bigserial primary key,
  org_id text not null,
  date date not null,
  amount numeric not null,
  category text,
  note text
);

-- For testing: open tables (no RLS). Later we can lock down with auth.
alter table public.sales disable row level security;
alter table public.expenses disable row level security;

3) Get Project URL + anon key (Settings → API)
4) Edit index.html, set SUPABASE_URL and SUPABASE_ANON.
5) Deploy on Vercel. Share link like: https://your-site.vercel.app/?org=inkhale
