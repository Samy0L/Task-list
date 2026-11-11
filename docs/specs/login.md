# Login page

Status: draft; awaiting the owner's review. Owner: project owner.

## Goal

Specify the first Task List login screen as a visual demo in Romanian, with a
dark theme, a username field and a password field. Users can try required-field
validation and see clear feedback that authentication is not connected.

The agreed frontend direction is Vue + Vite + TypeScript + Tailwind CSS.
Tailwind CSS will supply the styling when the owner configures the application.
The current task delivers documentation only; this draft is not an implemented
login page. The centered form and exact text below are proposed for review.

## Out of scope

- Task lists and task editing.
- Administration screens and permissions.
- Backend work, real credential verification, authentication API calls,
  account creation, sessions, credential storage and post-login navigation.
- Registration, password recovery and social sign-in.
- Email-format checks, username-format restrictions and password-strength or
  minimum-length rules; the demo only checks that required fields are filled.
- Remember-me controls, password visibility toggles and a theme switcher.
- Application scaffolding, dependency installation, Docker changes and deployment
  in this documentation task.

## Behavior

These are proposed acceptance behaviors for the later implementation. Unchecked
items are not passing tests; no application exists to exercise them yet.

- [ ] When I open the login page, I see a centered form on a dark background,
      the name "Task List", the heading "Conectare", the notice
      "Demonstrație vizuală", fields labeled "Nume de utilizator" and "Parolă",
      and a "Conectare" submit button, all readable in Romanian.
- [ ] When I type in "Parolă", the characters are masked.
- [ ] When I submit with an empty or whitespace-only username, I see
      "Introdu numele de utilizator." beside that field and remain on the page.
- [ ] When I submit with an empty password, I see "Introdu parola." beside that
      field and remain on the page. If both required fields are empty, I see
      both field messages.
- [ ] When I submit a nonblank username and a nonempty password, I see
      "Demonstrație: autentificarea nu este conectată." as form feedback and
      remain on the login page.
- [ ] After an invalid submission, when I fill both fields and submit again,
      the field errors disappear and I see the demo feedback. If I then clear
      a required field and submit, I see its error and the old demo feedback
      disappears.
- [ ] When I click either field's label, the corresponding input receives focus.
- [ ] When I use Tab, I can reach the username, password and submit button in
      that order with visible focus; when I press Enter in a field, I get the
      same validation or demo feedback as clicking "Conectare".
- [ ] When I view the page at viewport widths of 320 px and 1280 px, the form,
      labels, field errors and demo feedback remain readable and usable without
      horizontal scrolling.

## Done when

- [ ] The owner has approved this draft, including its exact text and layout.
- [ ] The later implementation uses Tailwind CSS for styling, confirmed by
      source review; this is not inferred from the page's appearance alone.
- [ ] Every behavior line has been checked in a browser.
- [ ] The repository check and any applicable application checks pass.
- [ ] The actual startup and verification steps are documented.
