# Design system

Build an original premium hybrid SaaS interface with comfortable density. Use Linear for precise alignment and interaction, Stripe for form feedback, Vercel for restrained composition, GitHub for useful navigation and accessible controls, and Vite for visual clarity. Express product identity through the [brand system](../branding/brand-identity.md).

Use server-rendered Blade layouts and reusable components. Use Tailwind semantic utilities mapped to shared tokens and Alpine for local interactions that benefit from JavaScript. Primary forms and links retain normal browser behavior. Load Geist with a system sans fallback and font swapping. Use English interface text, explicit labels, and one visually dominant primary action in a task region.

Offer Light, Dark, and System with labeled sun, moon, and monitor controls. Default to System and use the OS media query. Persist an explicit preference and respect changes to the OS while System is selected. Resolve the effective theme before first paint with a deployment-compatible CSP strategy, and keep the UI usable if storage is unavailable.

Read [tokens](design-tokens.md), [components](components.md), [accessibility](accessibility.md), and [responsive layout](responsive.md) before changing shared UI. Review new primitives across themes before adopting them in feature views.
