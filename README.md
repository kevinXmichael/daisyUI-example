## Calendly Integration

1. Create a free account
2. Choose a "friendly link name" with your alias
3. Connect calenders you use like Google Calender
4. Set your availability like Mo-Fr from 09:00 to 17:00
5. Last step: Just copy your link and use it as an `<a href="friendly_link_goes_here" target="_blank" />` on your website

## Send Emails

1. Use an SMTP relay service like [sendinblue](https://onboarding.sendinblue.com/account/register) and create a free account
2. Install [nodemailer](https://www.npmjs.com/package/nodemailer) and send an email with a [single connection transport](https://nodemailer.com/smtp/#1-single-connection)
3. When using [form actions](https://kit.svelte.dev/docs/form-actions) you need to decode the formData like this:

```ts
const data = await request.formData();
const email = data.get("email");
const password = data.get("password");
```

## Daisy UI Carousel

What you need to do first:

1. Install [tailwindcss](https://tailwindcss.com/docs/guides/sveltekit) for SvelteKit as well as daisyui

```bash
$ yarn add -D tailwindcss postcss autoprefixer daisyui
```

2. Add daisyui to your [tailwind.config.js](./tailwind.config.js)
3. Maybe have a look at [scroll snap](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type) which is the base of how a carousel "snaps"
4. Look into `Carousel.svelte` how I did it using [daisyUI Carousel example](https://daisyui.com/components/carousel/#slide3)
5. Tricky part is that you need to configure your app as a module in your `package.json` file with `"type": "module"`
6. Import tailwind in your `+layout.svelte` with the `app.css` file
7. Notice that the `postcss.config.cjs` and `tailwind.config.cjs` now end with `.cjs` which is just telling `Vite` that it compiles these files as [JavaScript Modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) now

## Header/Footer responsive width

TODO
