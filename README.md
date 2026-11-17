# StudyFlow — PHP

A responsive recreation of the supplied UUM StudyFlow references, using plain PHP, SQLite, CSS, JavaScript, and local images. No framework, Composer, database server, or build step is required.

## Run

With PHP 8.1 or newer, open PowerShell in this folder:

```powershell
.\start.ps1
```

Then open http://localhost:8000. The launcher enables PDO SQLite for this process if needed. Alternatively, use XAMPP PHP/Apache with `pdo_sqlite` enabled. For an already configured PHP installation, `php -S localhost:8000` also works.

## Included

- Responsive sky-blue landing page with 3D student artwork, five feature cards, illustrated steps, and an interactive dashboard preview. Get Started opens Login.
- Dedicated login and registration pages matching the supplied design, password visibility controls, 30-day Remember Me, and POST-only sign-out.
- Responsive dashboard with expanded/collapsed navigation, deadline calendar, task reminders, progress analytics and display settings.
- Accessible native dialogs for adding assignments and password-reset availability.
- PHP workspace: add, complete, reopen, delete, search, and filter assignments; upcoming deadlines and progress counts.
- Server-side validation, escaped user content, POST-only mutations, and CSRF protection.

Registered accounts and their assignments use SQLite. Passwords are hashed, remember-me tokens are stored as hashes and rotated on use, sessions are regenerated at login/logout, and failed login attempts are throttled per email/IP for 15 minutes. Queries for assignments are scoped to the signed-in account. The public demo continues to use temporary PHP session tasks and stays separate from account tasks.

The local database defaults to a project-specific `studyflow-*` directory under the system temporary directory, outside the public web root. It survives server restarts but system cleanup may remove it. For durable deployment, set `STUDYFLOW_DATA_DIR` to a persistent private directory outside the web root and back it up. The account does not validate university membership. UUM SSO, email verification, password reset emails, and email reminders are not connected. The Forgot Password dialog explains this limitation. This is an independent student project; use a separate StudyFlow password.

Google Fonts supplies Poppins, DM Sans and Manrope when online; local system fonts are used otherwise. All other visual assets are local. Landing page decorations have subtle floating effects and respect reduced-motion preferences. Sample preview tasks are separate from the account workspace.

## Assets

- Landing hero: generated `assets/studyflow-landing-students-v1.png`; the prompt is saved alongside it. The supporting UUM student illustration was supplied by the user. Login and Sign Up share the generated `assets/studyflow-auth-3d-v1.png` campus artwork; forms and buttons are live HTML/PHP.
- UUM logo: [Seekvectors](https://seekvectors.com/post/uum-logo). UUM branding belongs to Universiti Utara Malaysia.
- Current favicon: assets/logo.png. Icons, display masks, and decorative waves: project SVG/CSS.

The PHP built-in server is intended for local development. Deploy on a PHP-capable host with HTTPS, persistent private storage, backups, and configured account recovery.
# fauzi
