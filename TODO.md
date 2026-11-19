# TODO List

## Person 1 — Shared PHP Layout, About Page, and Packaging

- [ ] Set up project2/, convert the home page to index.php, and extract the
       shared layout into header.inc, nav.inc, and footer.inc as needed.
- [ ] Move CSS and images into styles/, images/, and styles/images/. Update
       navigation and asset links to use relative paths. Give the other
       members the shared layout early so they can use it on their pages.
- [ ] Create the about table and build about.php to load contributions from
       the database. Collect accurate summaries from all four members covering
       both Part 1 and Part 2.
- [ ] Combine the group’s SQL into one importable file, document local setup,
       and package the finished site as groupName_part2.zip. Include source
       and GenAI credits where used.
- [ ] Cross-test Person 3’s work: Verify the jobs page and search against the
       original job listings.

## Person 2 — Application form and EOI processing

- [ ] Convert the Part 1 application form to apply.php, preserve its fields,
       and POST to process_eoi.php. Disable browser validation with
       novalidate; enforce all validation on the server.
- [ ] Create the eoi table in PHP if it does not exist, with a column for
       every application field, an auto-generated EOInumber, and a status
       restricted to New, Current, or Final, defaulting to New.
- [ ] In process_eoi.php, redirect direct or empty requests. For submitted
       forms, trim and sanitise input, handle slashes as specified, validate
       required fields and formats, and show useful errors. Use a prepared
       statement to insert records and escape values when displaying them.
- [ ] Show the generated EOInumber on success. Share the EOI schema with
       Person 4 early and supply the matching schema for the submission SQL.
- [ ] Cross-test Person 4’s work: Verify login protection, filters, sorting,
       status updates, and deletion with test EOIs.

## Person 3 — Database Settings, Jobs Page, and Search

- [ ] Create settings.php with the local DB host, username, database name,
       and a blank database password. Make sure every database connection uses
       it.
- [ ] Create and seed the jobs table using all the content from the Part 1
       Jobs page. Use field types that match the data and agree on the job
       reference format with Persons 2 and 4.
- [ ] Build jobs.php to render all job details dynamically from the database.
       Add a search bar that submits to search.php and queries the database
       using prepared statements.
- [ ] Provide the jobs schema and seed data for the combined SQL file.
- [ ] Cross-test Person 1’s work: Follow navigation from index.php, check
       images and styles, and verify the About page loads all four
       contributions.

## Person 4 — Manager authentication and EOI management

- [ ] Create the user table and login/logout pages. Seed the marker account
       as admin / admin, store the password as a hash, and require an
       authenticated session to access manage.php.
- [ ] Add options to list all EOIs, filter by job reference, and filter by
       first name, last name, or both. Let the manager choose a sort field
       from an allowlist.
- [ ] Add controls to change an EOI’s status and delete all EOIs for a
       selected job reference. Use prepared statements, validate status
       values, and protect changes with POST and CSRF tokens. Ask for
       confirmation before bulk deletion.
- [ ] Provide the user schema and marker account seed for the combined SQL
       file.
- [ ] Cross-test Person 2’s work: Try a valid submission, invalid fields, and
       direct access to process_eoi.php; verify that only valid submissions
       create records.

## Before End

Rehersal for live demo + check database again
