---
project: "MC-ID"
title: "Introducing MC-ID"
description:
  "Introducing MC-ID, the most secure and convenient way to authenticate with your Minecraft
  account."
isPublic: true
type: "Release"
pubDate: "February 7, 2026"
heroImage: "/assets/images/mc-id/introducing-mc-id/banner.avif"
---

Today, we are excited to announce the launch of [**MC-ID**](https://mc-id.com), a brand-new
authentication platform designed to bridge the gap between your Minecraft identity and the
applications you use every day.

---

## Table of Contents

## The Problem with Minecraft Authentication

For years, players and developers have struggled with fragmented ways to verify Minecraft account
ownership. Most systems require users to join a specific "verification server" every single time
they want to log into a new website or link a service.

This process is slow, requires you to have the game open, and often lacks the security standards
expected of modern applications.

The official way of authenticating Minecraft accounts has been through Microsoft's OAuth, however,
this has been the source of many hostile takeovers and account breaches, as it exposes the full Xbox
login credentials to third-party applications, which can be easily used to fully take over the
account.

This has led to a lot of mistrust in the community towards using Microsoft OAuth for Minecraft
authentication.

## One Identity, Everywhere

**MC-ID** changes this by providing a centralized, secure, and universal sign-in method. Once you
have linked your Minecraft account with MC-ID, you can log in to any supported application
instantly; without ever needing to open your Minecraft client for subsequent logins.

It brings a "Login with MC-ID" experience that is as seamless as logging in with Google or Discord,
but built specifically for the Minecraft community.

## Built for Privacy and Security

Security is at the core of MC-ID. The platform is built on the latest **OAuth 2.1** and **OpenID
Connect (OIDC)** standards, featuring mandatory PKCE (Proof Key for Code Exchange) to ensure your
data stays safe.

- **Privacy First:** You are always in control. MC-ID only shares the data you explicitly authorize,
  such as your Minecraft UUID and username.
- **Secure by Design:** By using industry-standard protocols, we ensure that your credentials remain
  protected against unauthorized access.

## Developer Friendly

We built MC-ID with developers in mind. If you are building a community site, a guild dashboard, or
a marketplace, integrating MC-ID is incredibly simple. Because we are fully OIDC compliant, you can
use existing libraries like **Better Auth**, or **Passport.js** to add Minecraft authentication to
your app in minutes.

## Getting Started

To get started with MC-ID, simply visit [mc-id.com](https://mc-id.com) and link your Minecraft
account. Once linked, you can use MC-ID to log in to any supported application with just a few
clicks.

For Developers: Dive into [our documentation](https://docs.mc-id.com) to start integrating MC-ID
today.

MC-ID is also fully open source; we also provide a guide on how to self-host MC-ID if desired. We
believe in transparency and community-driven development. You can find our source code and
contribute to the project on [GitHub](https://github.com/Tonantzintla/MC-ID).

MC-ID will be used by many of our upcoming projects, including Unauctionable and another big project
we are a part of which we can't share the details of just yet.

Stay tuned for more updates as we continue to expand the MC-ID ecosystem!
