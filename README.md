# Tr3umphant.Designs 5.0 Website

Version 5 of Trey Hope's freelance portfolio site for Tr3umphant.Designs, a web and mobile app development service. It explains the service and the process for hiring Trey, shows past projects and client reviews, pulls in a blog from Blogger and has a contact form. It's an Angular 5 app from 2018 styled with Material Design for Bootstrap.

## Pages

Routes are defined in `src/app/routing.module.ts`:

| Path | Component | What it shows |
| --- | --- | --- |
| `/` | `HomeComponent` | hero: "The web and mobile app development service that you want." |
| `/about` | `AboutComponent` | what Tr3umphant.Designs is and how pricing works |
| `/service` | `ServiceComponent` | the step-by-step process for starting a project |
| `/projects` | `ProjectsComponent` | past work: Rightway Traffic Solutions, Tr3umphant-Designs 2.0, Intercom Marketing, a personal photo site, the tr3Designs Android/iOS store and Camp Central for iOS |
| `/reviews` | `ReviewsComponent` | client testimonials |
| `/blog` | `BlogsComponent` | development updates from Blogger |
| `/full-blog` | `FullBlogComponent` | a single post with share links |
| `/contact` | `ContactComponent` | name, email and message (400 characters max) form |
| `**` | `PageNotFoundComponent` | 404 page |

## How it works

- **Blog** (`src/app/services/blog.service.ts`) loads posts from the Blogger API v3, using the blog ID and API key set in that service.
- **Contact** (`src/app/services/email.service.ts`) posts the form as JSON to `src/assets/sendEmailJSON.php` (`sendEmailMulti.php` is an alternate script), so the built site needs a PHP host that can send mail.
- Images live in `img/`.

## Tech stack

- Angular 5 with the Angular CLI (`.angular-cli.json`)
- Material Design for Bootstrap (`angular-bootstrap-md`)
- Blogger API v3, PHP mail scripts
- Karma + Jasmine and Protractor (CLI defaults)

## Getting started

Requires a Node.js version that Angular CLI 1.x supports (Node 8 or 10).

```sh
npm install
npm start          # ng serve on http://localhost:4200
npm run build      # ng build --prod, output in dist/
```

Upload `dist/` to a PHP-capable host so the contact form works.
