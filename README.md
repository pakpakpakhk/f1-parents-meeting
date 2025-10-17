[README.txt](https://github.com/user-attachments/files/22965530/README.txt)
F.1 Parents Meeting — GitHub Pages (with parent counts & teacher dashboard)
=============================================================================

Files:
- index.html         → Parent check-in (records 1–3 parents per family)
- teacher.html       → Teacher dashboard (students & parents totals + CSV export)
- students_data.json → Roster + venues (from your Excel)
- supabase_setup.sql → Table + RLS policies for live syncing (optional)

How to publish on GitHub Pages
------------------------------
1) New GitHub repo (public). Upload: index.html, teacher.html, students_data.json
2) Settings → Pages → Deploy from a branch (main / root).
3) Visit your URL:
   - Parent page:   .../index.html
   - Teacher page:  .../teacher.html

Enable live syncing with Supabase (optional)
--------------------------------------------
1) In Supabase → SQL Editor → run **supabase_setup.sql** (creates table `checkins` + policies)
2) Copy Project URL + Anon key.
3) Edit both HTML files: at the top, fill the inline <script>:
   window.SUPABASE_URL = "https://YOUR.supabase.co";
   window.SUPABASE_ANON = "YOUR_PUBLIC_ANON_KEY";
   window.SUPABASE_TABLE = "checkins";

That’s it. Parents’ check-ins will appear on the teacher page from any device.
