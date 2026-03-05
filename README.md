<div align="center">

# Awesome RxJS [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

**A curated collection of awesome [RxJS](https://rxjs.dev) resources, libraries, tools, and frameworks**

*RxJS is a library for composing asynchronous and event-based programs using observable sequences. It provides one core type, the Observable, satellite types (Observer, Schedulers, Subjects) and operators inspired by Array methods to allow handling asynchronous events as collections.*

[![RxJS](https://img.shields.io/npm/v/rxjs?label=RxJS&color=B7178C&logo=reactivex)](https://www.npmjs.com/package/rxjs)
[![GitHub Stars](https://img.shields.io/github/stars/ReactiveX/rxjs?style=flat&color=B7178C)](https://github.com/ReactiveX/rxjs)
[![License: CC0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

[Official Docs](https://rxjs.dev) · [GitHub](https://github.com/ReactiveX/rxjs) · [npm](https://www.npmjs.com/package/rxjs) · [Stack Overflow](https://stackoverflow.com/questions/tagged/rxjs)

</div>

---

## Contents

- [Official Resources](#official-resources)
- [Getting Started](#getting-started)
- [Intermediate & Advanced](#intermediate--advanced)
- [Hot vs Cold Observables](#hot-vs-cold-observables)
- [The Reactive Timeline](#the-reactive-timeline)
- [Frameworks Using RxJS](#frameworks-using-rxjs)
- [State Management](#state-management)
- [React & RxJS](#react--rxjs)
- [Libraries & Utilities](#libraries--utilities)
- [Testing](#testing)
- [Debugging](#debugging)
- [Linting](#linting)
- [Data & Persistence](#data--persistence)
- [Books](#books)
- [Video Courses](#video-courses)
- [Talks](#talks)
- [Articles](#articles)
- [Interactive Tools](#interactive-tools)
- [Community](#community)
- [The Observable Standard](#the-observable-standard)
- [Related Reactive Libraries](#related-reactive-libraries)
- [People](#people)

---

## Official Resources

- [rxjs.dev](https://rxjs.dev) — Official documentation, API reference, and guides.
- [ReactiveX/rxjs](https://github.com/ReactiveX/rxjs) — Official GitHub repository (RxJS 7+).
- [RxJS Operator Decision Tree](https://rxjs.dev/operator-decision-tree) — Interactive guide to help you pick the right operator.
- [RxJS API List](https://rxjs.dev/api) — Complete API reference for all operators, creation functions, and utilities.

## Getting Started

*New to reactive programming? Start here.*

- [The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) — The legendary introductory gist by André Staltz. A rite of passage for every reactive programmer.
- [Learn RxJS](https://www.learnrxjs.io) — Clear, concise descriptions, examples, and resources for RxJS operators by Brian Troncone. One of the most-loved community resources.
- [RxJS Marbles](https://rxmarbles.com) — Interactive marble diagrams for every RxJS operator by André Staltz.
- [Reactive.how](https://reactive.how) — Beautiful animated cards to learn reactive programming by Cédric Soulas.
- [LearnRx](http://reactivex.io/learnrx/) — Interactive operator tutorial from ReactiveX.
- [Introduction to Reactive Programming](https://egghead.io/series/introduction-to-reactive-programming) — Egghead series by André Staltz for those *brand new* to reactive programming.
- [Step-by-Step Async JavaScript with RxJS](https://egghead.io/series/step-by-step-async-javascript-with-rxjs) — Egghead series by John Lindquist.
- [Introducing the Observable](https://egghead.io/lessons/javascript-introducing-the-observable) — Egghead series by Jafar Husain.
- [Rx Visualizer](https://rxviz.com) — Animated playground for Rx Observables by Misha Moroshko.
- [RxJS Operator Decision Tree](https://rxjs.dev/operator-decision-tree) — Not sure which operator to use? This interactive tree helps you find the right one.

## Intermediate & Advanced

*Ready to go deeper? These resources will level you up.*

- [RxJS Beyond the Basics: Creating Observables from scratch](https://egghead.io/series/rxjs-beyond-the-basics-creating-observables-from-scratch) — Egghead series by André Staltz.
- [RxJS Beyond the Basics: Operators in Depth](https://egghead.io/series/rxjs-beyond-the-basics-operators-in-depth) — Egghead series by André Staltz.
- [RxJS Patterns & Best Practices](https://www.learnrxjs.io) — Practical patterns and anti-patterns at Learn RxJS.
- [Online RxJS Reference Book](https://xgrommx.github.io/rx-book/index.html) — Comprehensive online gitbook by Denis Stoyanov (xgrommx).
- [Awesome Functional Programming](https://github.com/xgrommx/awesome-functional-programming) — Companion resource by Denis Stoyanov.

## Hot vs Cold Observables

[Paul Taylor](https://twitter.com/trxcllnt) (RxJS core contributor) with one of the best explanations of Hot & Cold Observables:

> "cold" and "hot" don't refer to unicast vs. multicast, they refer to the state of the computation. An Observable represents an asynchronous computation (aka, it's a function that can return multiple values between now and infinity).
>
> "Cold" Observables are just like functions which haven't been called (subscribed to) yet. Each time you call it (aka, subscribe to it), you're re-running whatever calculation the Observable performs.
>
> "Hot" Observables are just regular cold Observables that you've shoved a Subject between you and the cold Observable source. When you subscribe to it, you're really subscribing to the Subject over and over.

*[Source: ReactiveX/RxJS#1121](https://github.com/ReactiveX/RxJS/issues/1121#issuecomment-169568428)*

## The Reactive Timeline

*RxJS didn't appear out of nowhere. It is the JavaScript chapter of a story that spans three decades, multiple languages, and some of the most elegant ideas in computer science. Here is that journey.*

```
  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║                                                                             ║
  ║           ◆  THE REACTIVE TIMELINE  ◆                                       ║
  ║           From Observer Pattern to Native Browser Observables               ║
  ║                                                                             ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝


  ── THE FOUNDATIONS ──────────────────────────────────────────────────────────────

            │
    1994    ●─── The Observer Pattern
            │    Erich Gamma, Richard Helm, Ralph Johnson & John Vlissides
            │    publish "Design Patterns: Elements of Reusable Object-Oriented
            │    Software" — the Gang of Four book. Chapter 5 defines the
            │    Observer pattern: a one-to-many dependency where objects are
            │    notified automatically of state changes. The seed is planted.
            │
            │
    1997    ●─── Functional Reactive Animation
            │    Conal Elliott & Paul Hudak at Yale publish "Functional Reactive
            │    Animation" (ICFP '97), introducing the concept of continuous
            │    time-varying values ("Behaviors") and discrete event streams
            │    ("Events") composed with pure functions. This paper gives birth
            │    to Functional Reactive Programming (FRP) — the theoretical
            │    ancestor of everything that follows.
            │
            │
    2005    ●─── The Duality Insight
            │    Erik Meijer at Microsoft Research has a breakthrough: he
            │    recognizes that IObservable<T> is the mathematical dual of
            │    IEnumerable<T>. Where Enumerable lets you PULL values
            │    synchronously, Observable lets you PUSH values asynchronously.
            │    Same algebra, opposite direction. This elegant insight becomes
            │    the foundation of Reactive Extensions.
            │
            │        ┌─────────────────────────────────────────────┐
            │        │  IEnumerable<T>  ←──dual──→  IObservable<T> │
            │        │                                             │
            │        │  Pull / Synchronous    Push / Asynchronous  │
            │        │  Iterator.next()       Observer.onNext()    │
            │        │  try/catch             Observer.onError()   │
            │        │  return                Observer.onCompleted()│
            │        └─────────────────────────────────────────────┘
            │
            │
    2007    ●─── Flapjax
            │    Leo Meyerovich and team at Brown University create Flapjax,
            │    one of the first FRP languages for the web. It compiles to
            │    JavaScript and demonstrates that reactive programming can
            │    work in browsers. A proof of concept ahead of its time.
            │

  ── THE BIRTH OF Rx ─────────────────────────────────────────────────────────────

            │
    2009    ●─── Rx.NET 1.0
            │    Erik Meijer's team at Microsoft DevLabs releases Reactive
            │    Extensions for .NET — the first Rx library. It ships as
            │    System.Reactive. LINQ-style operators (Select, Where,
            │    SelectMany) applied to push-based streams. Developers can
            │    now compose asynchronous event sequences as elegantly as
            │    they query collections. The reactive revolution begins.
            │
            │
    2010    ●─── Rx Goes Open Source & RxJS is Born
            │    Microsoft open-sources Reactive Extensions under the Apache
            │    2.0 license. Matthew Podwysocki leads the effort to create
            │    RxJS — the first JavaScript port of Rx. It brings Observable,
            │    Observer, and the operator algebra to the browser.
            │
            │

  ── THE EXPANSION ───────────────────────────────────────────────────────────────

            │
    2012    ●─── RxJava at Netflix
            │    Ben Christensen and Jafar Husain at Netflix create RxJava to
            │    handle the massive scale of Netflix's microservices. Reactive
            │    patterns prove they can work at Netflix scale — millions of
            │    concurrent streams across thousands of devices. The success
            │    of RxJava brings Rx into the mainstream.
            │
            │
    2013    ●─── ReactiveX Unifies the Ecosystem
            │    ReactiveX.io launches as a cross-language initiative, unifying
            │    Rx implementations under one banner: RxJava, RxJS, Rx.NET,
            │    RxSwift, RxKotlin, RxPY, RxRuby, RxScala, and more.
            │    "An API for asynchronous programming with observable streams."
            │
            │    Meanwhile, Juha Paananen releases Bacon.js, bringing FRP
            │    concepts to mainstream JavaScript with an accessible API.
            │
            │
    2014    ●─── RxJS 4 Matures
            │    The Microsoft-era RxJS (Reactive-Extensions/RxJS) reaches
            │    version 4 — a full-featured, battle-tested library. But the
            │    codebase is showing its age: large bundles, hard to debug,
            │    and difficult to tree-shake.
            │
            │    Jafar Husain's "Async Programming in ES7" talk at Netflix
            │    previews the idea of Observable as a language primitive.
            │
            │

  ── THE REWRITE ─────────────────────────────────────────────────────────────────

            │
    2015    ●─── A Pivotal Year
            │
            │    ┌ MAY ── Jafar Husain submits the Observable proposal to
            │    │        TC39. It reaches Stage 1. The dream: Observable
            │    │        as a native JavaScript type.
            │    │
            │    ├ JUN ── André Staltz publishes "The introduction to
            │    │        Reactive Programming you've been missing" — a
            │    │        gist that becomes the most-shared RP resource
            │    │        ever. He also creates Cycle.js and RxMarbles.
            │    │
            │    └ OCT ── Ben Lesh begins the RxJS 5 rewrite from scratch
            │             with Paul Taylor. Goals: performance, modularity,
            │             debuggable stack traces, and compliance with the
            │             TC39 Observable spec.
            │
            │
    2016    ●─── RxJS 5 & Angular 2
            │    Ben Lesh and Paul Taylor ship RxJS 5 — a ground-up rewrite
            │    under the ReactiveX GitHub org. Faster, smaller, with proper
            │    class-based Observables and Symbol.observable support.
            │
            │    Google's Angular 2 launches with RxJS as a core dependency.
            │    Overnight, millions of Angular developers become RxJS users.
            │    Observable goes from niche to mainstream.
            │
            │

  ── THE MODERN ERA ──────────────────────────────────────────────────────────────

            │
    2017    ●─── The Ecosystem Flourishes
            │    NgRx brings Redux-style reactive state management to Angular.
            │    NestJS launches with deep RxJS integration on the server.
            │    Nicholas Jamieson (cartant) begins building essential tools:
            │    rxjs-spy, rxjs-marbles, eslint-plugin-rxjs, rxjs-etc.
            │    The WHATWG DOM Observable issue is filed — a new path toward
            │    standardization.
            │
            │
    2018    ●─── RxJS 6: The pipe() Revolution
            │    Pipeable operators replace dot-chaining. Tree-shaking finally
            │    works. Bundle sizes shrink dramatically. The API becomes
            │    cleaner and more functional:
            │
            │        // Before (RxJS 5)              // After (RxJS 6)
            │        // source.map(x => x * 2)       // source.pipe(
            │        //       .filter(x => x > 5)    //   map(x => x * 2),
            │        //       .subscribe(...)         //   filter(x => x > 5)
            │        //                               // ).subscribe(...)
            │
            │
    2019    ●─── RxJS Live
            │    Tracy Lee and This Dot Labs organize the world's first
            │    conference dedicated entirely to RxJS in Las Vegas. Ben Lesh
            │    delivers the keynote. The community has a home.
            │
            │
    2021    ●─── RxJS 7: Lean & Precise
            │    53% smaller bundle than v6. Better TypeScript types.
            │    toPromise() deprecated for firstValueFrom/lastValueFrom.
            │    New operators: animationFrames(), switchScan(). AsyncIterable
            │    support everywhere. The library is mature and battle-hardened.
            │
            │

  ── THE NATIVE FUTURE ───────────────────────────────────────────────────────────

            │
    2023    ●─── The Observable Proposal Revived
            │    Ben Lesh and Dominic Farolino (Google) revive the Observable
            │    proposal at WICG/WHATWG — this time as a Web Platform API
            │    rather than a TC39 language primitive. Chromium implementation
            │    begins. RxJS 8 development is deliberately paused to align
            │    with the native API.
            │
            │
    2025    ●─── Observable Goes Native
            │    The Observable API ships in Chrome 135 and Chromium-based
            │    browsers. After 10 years, Observable is finally a browser
            │    primitive. RxJS's future role: extend and enrich the native
            │    Observable with the rich operator library developers love.
            │
            │    Meanwhile, Angular adopts Signals for synchronous reactivity
            │    alongside RxJS for asynchronous streams — proving that the
            │    reactive story continues to evolve.
            │
            ▼
         ┌─────────────────────────────────────────────────────────┐
         │                                                         │
         │   "The future is already here — it's just not evenly    │
         │    distributed."                                        │
         │                                     — William Gibson    │
         │                                                         │
         └─────────────────────────────────────────────────────────┘
```

### RxJS Version History

| Version | Era | Key Innovation |
|---------|-----|----------------|
| **RxJS 4** | 2012–2015 | The original JS implementation of Reactive Extensions. Microsoft-era. |
| **RxJS 5** | 2016–2018 | Complete rewrite by Ben Lesh & Paul Taylor. Adopted by Angular. |
| **RxJS 6** | 2018–2020 | Pipeable operators (`pipe()`), tree-shakeable imports. |
| **RxJS 7** | 2021–present | 53% smaller, better TypeScript types. Current stable: **7.8.2**. |
| **RxJS 8** | On Hold | Paused to align with native browser Observables (Chrome 135+). |

**Key RxJS 7 Features:**
- 53% smaller bundle size than v6 (~19 KB vs ~52 KB)
- Better TypeScript types (4.2+) — `of()` infers 9+ params, `filter(Boolean)` narrows types
- `toPromise()` deprecated in favor of `firstValueFrom()` / `lastValueFrom()`
- AsyncIterable support everywhere Observables are accepted
- Simplified multicasting with improved `share()` operator
- New operators: `animationFrames()`, `switchScan()`

**Repositories:**
- [ReactiveX/RxJS](https://github.com/ReactiveX/rxjs) — Current (RxJS 5+)
- [Reactive-Extensions/RxJS](https://github.com/Reactive-Extensions/RxJS) — Legacy (RxJS 4)

## Frameworks Using RxJS

*Frameworks and platforms with deep RxJS integration.*

- [Angular](https://angular.dev) — Google's platform for building web applications. RxJS is a core dependency powering forms, HTTP, routing, and state management. Angular 20+ offers Signal/Observable interop via `@angular/core/rxjs-interop`.
- [NestJS](https://nestjs.com) — Progressive Node.js framework for building server-side applications. Uses RxJS in HTTP interceptors, microservices, and event handling.
- [Cycle.js](https://cycle.js.org) — A fully reactive JavaScript framework for Human-Computer Interaction by André Staltz. Every app is a pure function from input streams to output streams.
- [Marble.js](https://docs.marblejs.com) — Functional reactive Node.js framework built entirely on TypeScript and RxJS. Core concept: everything is a stream. Supports HTTP, WebSocket, and microservices.
- [Stencil](https://stenciljs.com) — Web Component compiler by Ionic. Works well with RxJS for reactive component patterns.

## State Management

*State management solutions built on or deeply integrated with RxJS.*

### Angular Ecosystem

- [NgRx](https://ngrx.io) — The most popular RxJS-powered state management for Angular, inspired by Redux. Includes `@ngrx/store`, `@ngrx/effects`, `@ngrx/entity`, `@ngrx/component-store`, and the newer `@ngrx/signals` (SignalStore). v21+ available.
- [rx-angular](https://github.com/rx-angular/rx-angular) — Comprehensive toolkit for fully reactive, high-performance Angular applications by Michael Hladky and the Push-Based team. Includes `@rx-angular/state`, `@rx-angular/template`, `@rx-angular/cdk`, and `@rx-angular/isr`.
- [NGXS](https://www.ngxs.io) — State management for Angular modeled after CQRS. Uses TypeScript classes and decorators to reduce boilerplate compared to NgRx.
- [Elf](https://ngneat.github.io/elf/) — A reactive immutable state management solution built on top of RxJS. Successor to Akita. Tree-shakeable and modular.
- [Akita](https://github.com/salesforce/akita) — State management built on RxJS using the Observable Data Stores model. *Archived as of May 2025; succeeded by Elf.*

### React Ecosystem

- [redux-observable](https://redux-observable.js.org) — RxJS-based middleware for Redux using "Epics" — functions that take a stream of actions and return a stream of actions. Created by Jay Phelps. *In maintenance mode.*

### Framework-Agnostic

- [RxDB](https://rxdb.info) — Also works as a state management layer. See [Data & Persistence](#data--persistence).

## React & RxJS

*Integrating the power of RxJS with the React component model.*

- [observable-hooks](https://observable-hooks.js.org) — React hooks for RxJS Observables. Concurrent mode safe, Suspense-compatible, 100% test coverage. The recommended way to use RxJS with React. Compatible with RxJS 6 & 7.
- [rxjs-hooks](https://github.com/LeetCode-OpenSource/rxjs-hooks) — React hooks for RxJS by LeetCode. Provides `useObservable` and `useEventCallback`. *Note: Does not work properly with React 18+ StrictMode.*

## Libraries & Utilities

*Operators, helpers, and utilities that extend RxJS.*

- [rxjs-etc](https://github.com/cartant/rxjs-etc) — A grab-bag of additional observables and operators for RxJS by Nicholas Jamieson. Includes `combineLatestArray`, `debounceSync`, `concatMapEager`, and more.
- [rxjs-ninja](https://rxjs-ninja.tane.dev) — Modular set of RxJS operators for working with strings, numbers, booleans, arrays, and more. Includes `mapIf`, `tapOnFirstEmit`, `fromEventSource`, and `fromReadableStream`.
- [backoff-rxjs](https://github.com/alex-okrushko/backoff-rxjs) — RxJS operators for exponential backoff strategies. Provides `intervalBackoff` and `retryBackoff` by Alex Okrushko.
- [rxjs-websockets](https://github.com/insidewhy/rxjs-websockets) — Flexible, cold-observable-based WebSocket library for RxJS. Supports browser and Node.js.
- [rxjs-for-await](https://github.com/benlesh/rxjs-for-await) — Makes RxJS Observables work with async-await `for await...of` loops via AsyncIterables by Ben Lesh.
- [subscribable-things](https://github.com/nicedoc/subscribable-things) — Collection of reactive wrappers for browser APIs (mediaDevices, mediaQueryMatch, IntersectionObserver, MutationObserver, ResizeObserver).

### Angular-Specific Utilities

- [@ngneat/until-destroy](https://github.com/ngneat/until-destroy) — Automatic unsubscription for Angular components when they are destroyed. Essential for preventing memory leaks.
- [ngx-operators](https://github.com/nicedoc/ngx-operators) — Collection of Angular-specific RxJS operators (`prepare`, `indicate`, `download`, and more).

## Testing

*Tools and techniques for testing RxJS code.*

- [RxJS TestScheduler](https://rxjs.dev/guide/testing/marble-testing) — Built-in marble testing with `TestScheduler`. The official way to test time-dependent Observable code.
- [rxjs-marbles](https://github.com/cartant/rxjs-marbles) — RxJS marble testing library compatible with any test framework (Jest, Jasmine, Mocha, AVA, Tape) by Nicholas Jamieson.
- [rx-sandbox](https://github.com/kwonoj/rx-sandbox) — Marble diagram DSL-based test suite for RxJS. Provides visual diffs for debugging failed tests.
- [observer-spy](https://github.com/hirezio/observer-spy) — Simple testing of RxJS Observables without marble diagrams. Great alternative when timing isn't critical for your tests.
- [How To Debug RxJS Code](http://staltz.com/how-to-debug-rxjs-code.html) — André Staltz's guide to debugging RxJS.
- [Testing Reactive Code](https://glebbahmutov.com/blog/testing-reactive-code/) — Dr. Gleb Bahmutov's guide to testing RxJS.
- [RxJS Testing in Real World Applications](https://blog.hyphe.me/rxjs-testing-in-real-world-applications/) — Practical testing patterns by Simon Jentsch.
- [How to Easily Write and Debug RxJS Marble Tests](https://mokkapps.de/blog/how-to-easily-write-and-debug-rxjs-marble-tests) — Visual guide to marble testing by Michael Hoffmann.

## Debugging

*Tools to help you understand what your Observables are doing.*

- [rxjs-spy](https://github.com/cartant/rxjs-spy) — Debugging library by Nicholas Jamieson. Tag observables, then monitor, pause, and replay them from the browser console. Features `log`, `pause`, `let`, and `undo` console APIs.
- [RxJS DevTools](https://github.com/nicedoc/rxjs-devtools) — Browser extension for visualizing Observable streams and their interactions over time.

## Linting

*Static analysis rules to keep your RxJS code clean and safe.*

- [eslint-plugin-rxjs-x](https://github.com/JasonWeinzierl/eslint-plugin-rxjs-x) — Actively maintained ESLint rules for RxJS. Supports ESLint v9 flat config. Includes rules like `no-floating-observables`, `no-async-subscribe`, `no-unsafe-switchmap`, `no-unsafe-takeuntil`, and more. The recommended choice for new projects.
- [eslint-plugin-rxjs-angular-x](https://github.com/JasonWeinzierl/eslint-plugin-rxjs-angular-x) — Angular-specific RxJS ESLint rules.
- [@smarttools/eslint-plugin-rxjs](https://github.com/DaveMBush/eslint-plugin-rxjs) — Community fork supporting ESLint v9 flat config.
- [eslint-plugin-rxjs](https://github.com/cartant/eslint-plugin-rxjs) — The original ESLint rules for RxJS by Nicholas Jamieson. *Note: Supports ESLint ≤8 only.*

## Data & Persistence

*Reactive data layers powered by RxJS.*

- [RxDB](https://rxdb.info) — A local-first, offline-capable, reactive NoSQL database for JavaScript by Daniel Meyer. Subscribe to query results in real-time. Supports IndexedDB, OPFS, SQLite, and more. Replication via HTTP, GraphQL, CouchDB, WebSocket, WebRTC, Supabase, and Firestore. Current version: **16.x**.
- [apollo-angular](https://github.com/the-guild-org/apollo-angular) — Production-ready GraphQL client for Angular with native RxJS integration. `.valueChanges` returns Observables.
- [apollo-client-rxjs](https://github.com/kamilkisiela/apollo-client-rxjs) — Wraps Apollo Client queries as RxJS Observables.
- [reactive-graphql](https://github.com/mesosphere/reactive-graphql) — Standalone GraphQL implementation built around RxJS.

## Books

- **[RxJS in Action](https://www.manning.com/books/rxjs-in-action)** — *Paul P. Daniels & Luis Atencio* (Manning, 2017). Foreword by Ben Lesh. Deep theory and practical examples. Covers error handling, testing, and integration with React and Redux.
- **[Build Reactive Websites with RxJS](https://pragprog.com/titles/rkrxjs/build-reactive-websites-with-rxjs/)** — *Randall Koutnik* (Pragmatic Programmers, 2018). Hands-on, project-based. From fundamentals to building a canvas game. By a senior engineer at Netflix.
- **[Reactive Programming with RxJS 5](https://pragprog.com/titles/smreactjs5/reactive-programming-with-rxjs-5/)** — *Sergi Mansilla* (Pragmatic Programmers). Conceptual foundation with creative examples including a real-time earthquake visualization and a space shooter game.
- **[Reactive Patterns with RxJS and Angular Signals](https://www.packtpub.com/en-us/product/reactive-patterns-with-rxjs-and-angular-signals-9781835087701)** — *Lamis Chebbi* (Packt, 2nd Edition). Step-by-step guide covering RxJS 7 and Angular Signals interop.
- **[RxJS Cookbook for Reactive Programming](https://www.packtpub.com/en-us/product/rxjs-cookbook-for-reactive-programming-9781788624053)** — *Nikola Mitrovic* (Packt). 40+ real-world solutions for building async, event-driven web apps.
- **[The Illustrated Book of RxJS](https://cedricsoulas.gumroad.com/l/illustrated-rxjs)** — *Cédric Soulas*. 400+ pages of beautiful visual operator illustrations. Available on Gumroad.

### Free Online Books

- **[rx-book](https://xgrommx.github.io/rx-book/index.html)** — Comprehensive free online reference by Denis Stoyanov (xgrommx).
- **[Learn RxJS](https://softchris.github.io/books/rxjs/)** — Free online RxJS book by Chris Noring.

## Video Courses

### Free

- [Introduction to Reactive Programming](https://egghead.io/series/introduction-to-reactive-programming) — André Staltz on Egghead. The perfect starting point.
- [Thinking Reactively with RxJS](https://egghead.io/courses/thinking-reactively-with-rxjs) — Rares Matei on Egghead. Learn the reactive mindset.
- [Cycle.js Fundamentals](https://egghead.io/courses/cycle-js-fundamentals) — André Staltz on Egghead.
- [Free RxJS Training by Ben Lesh](https://www.thisdot.co/blog/learn-rxjs-from-ben-lesh-free-rxjs-training-during-the-javascript-marathon) — Free live sessions covering Observables, operators, Subjects, multicasting, and common mistakes. By This Dot Labs.
- [State of RxJS Panels](https://www.youtube.com/@thisdotmedia) — Panel discussions about the current state and future of RxJS. This Dot Media YouTube channel.
- [RxJS Live Conference Talks](https://www.youtube.com/@RxJSLive) — All recordings from the world's first RxJS-focused conference (Las Vegas, 2019).

### Paid

- [Ultimate RxJS Basics](https://ultimatecourses.com/author/briantroncone) — Brian Troncone on Ultimate Courses. 5/5 rating, 6,800+ reviews.
- [RxJS Masterclass](https://ultimatecourses.com/author/briantroncone) — Brian Troncone on Ultimate Courses. 4.9/5 rating, 4,400+ reviews.
- [Asynchronous Programming in JavaScript](https://frontendmasters.com/courses/asynchronous-javascript/) — Jafar Husain on Frontend Masters. The Netflix async patterns that started it all.

## Talks

*Conference talks that shaped the RxJS community.*

### Foundational

- [What if the user was a function?](https://www.youtube.com/watch?v=1zj7M1LnJV4) — André Staltz (Jun 2015). The talk that introduced many to Cycle.js and reactive UI thinking.
- [Async Programming in ES7](https://www.youtube.com/watch?v=lil4YCCXRYc) — Jafar Husain (Jul 2014). Netflix's async patterns that influenced the Observable proposal.
- [Controlling Time and Space: understanding the many formulations of FRP](https://www.youtube.com/watch?v=Agu6jipKfYw) — Evan Czaplicki (Sep 2014). The theoretical foundations of FRP.
- [Reactive JavaScript at Netflix, Microsoft and the World](https://www.youtube.com/watch?v=KOOT7BArVHQ) — Matthew Podwysocki (Dec 2015). The reactive vision across the industry.

### Modern

- [RxJS Live 2019 Keynote](https://www.youtube.com/c/RxJSLive) — Ben Lesh on the future of RxJS at the world's first RxJS conference.
- [dotJS 2024 — Ben Lesh](https://www.conferencecast.tv/speaker-38293-ben-lesh) — Thinking about categorizing code: push vs pull. A genuinely great modern talk.
- [4 Wicked RxJS Pipelines for the Real World](https://www.youtube.com/results?search_query=deborah+kurata+rxjs+pipelines+ng-conf) — Deborah Kurata (ng-conf 2021). Practical Subjects, creation functions, and higher-order mapping.
- [Mastering the Subject: Communication Options in RxJS](https://blog.codewithdan.com/ng-conf-talk-mastering-the-subject-communication-options-in-rxjs/) — Dan Wahlin. Covers Subject, BehaviorSubject, ReplaySubject, AsyncSubject.
- [RxJS Schedulers from Outer Space](https://www.youtube.com/results?search_query=michael+hladky+rxjs+schedulers) — Michael Hladky. Advanced patterns for performance, animations, and asynchrony.

## Articles

### Essential Reads

- [The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) — André Staltz. *The* canonical introduction. The most-starred gist on GitHub.
- [2 Minute Introduction to Rx](https://medium.com/@andrestaltz/2-minute-introduction-to-rx-24c8ca793877) — André Staltz. The shortest path to understanding Rx.
- [Learning Observable By Building Observable](https://benlesh.com/posts/learning-observable-by-building-observable/) — Ben Lesh (2021). Understand the Observable type by building one.
- [Observables, Reactive Programming, and Regret](https://dev.to/benlesh) — Ben Lesh (2020). Honest reflections on the RxJS journey. 790+ reactions.
- [The Two Pillars of JavaScript — Pt 2: Functional Programming](https://medium.com/javascript-scene/the-two-pillars-of-javascript-pt-2-functional-programming-a63aa53a41a4) — Eric Elliott.

### Patterns & Best Practices

- [Containers Are Dead. Long Live Observable Combinators](https://medium.com/@milankinen/containers-are-dead-long-live-observable-combinators-2cb0c1f06c96) — Matti Lankinen (Nov 2015).
- [RxJS Best Practices in Angular](https://www.infoq.com/articles/rxjs-angular16-best-practices/) — AsyncPipe, flattening streams, takeUntil with DestroyRef, catchError and retry patterns.
- [Automating RxJS Cleanup: How Halodoc Eliminated Angular Memory Leaks](https://blogs.halodoc.io/eliminating-angular-memory-leaks-in-the-halodoc-website-with-generators-2/) — Real-world memory leak prevention at scale.
- [Angular & RxJS in 2025: The Expert's Playbook](https://dev.to/cristiansifuentes/angular-rxjs-in-2025-the-experts-playbook-signals-rxjs-8-and-interop-28ed) — Signals, RxJS 8, and interop patterns.
- [Will Signals Replace RxJS?](https://angularexperts.io/blog/signals-vs-rxjs/) — Angular Experts. Consensus: Signals for local/UI state, RxJS for async/complex streams.

### Tutorials

- [Angular — Introduction to Reactive Extensions (RxJS)](https://medium.com/google-developer-experts/angular-introduction-to-reactive-extensions-rxjs-a86a7430a61f) — Gerard Sans (Sep 2015).
- [A Dead-Simple Todo List with RxJS](http://blog.edanschwartz.com/2015/09/18/dead-simple-rxjs-todo-list) — Edan Schwartz (Sep 2015).
- [Testing RxJS Observables Just Became Super Simple](https://medium.com/@shairez/testing-rxjs-observables-just-became-super-simple-using-observer-spies-93a25eb567bd) — Shai Reznik. Using observer-spy.

## Interactive Tools

*Visualize, explore, and experiment with RxJS.*

- [RxJS Marbles](https://rxmarbles.com) — Interactive marble diagrams by André Staltz.
- [Rx Visualizer](https://rxviz.com) — Animated playground for Rx Observables by Misha Moroshko.
- [ThinkRx](https://thinkrx.io/rxjs/) — Instant marble diagram playground. Supports RxJS 5 and 6 style.
- [Reactive.how](https://reactive.how) — Animated cards for learning reactive operators by Cédric Soulas.
- [RxJS Operator Decision Tree](https://rxjs.dev/operator-decision-tree) — Official interactive guide for choosing operators.
- [DevDocs — RxJS](https://devdocs.io/rxjs/) — Offline-capable API docs with instant search.

## Community

### Discussion & Q&A

- [RxJS GitHub Discussions](https://github.com/ReactiveX/rxjs/discussions) — Official discussions on the RxJS GitHub repo.
- [Stack Overflow — rxjs tag](https://stackoverflow.com/questions/tagged/rxjs) — Thousands of answered questions.
- [ReactiveX Community Hub](https://reactivex.io/community.html) — Gitter rooms, StackOverflow tags, and community projects.

### Conferences & Events

- [RxJS Live](https://www.rxjs.live/) — The world's first and only RxJS-focused conference.
- [This Dot Labs — RxJS Community](https://www.thisdot.co/services/technologies/rxjs) — Community events, training, and panels.

### Podcasts

- [Software Engineering Daily — RxJS with Ben Lesh](https://softwareengineeringdaily.com/2025/07/29/rxjs-with-ben-lesh/) — In-depth interview about RxJS past, present, and future (Jul 2025).
- [Adventures in Angular](https://topenddevs.com/podcasts/adventures-in-angular) — Multiple episodes covering practical RxJS applications, rx-angular, and reactive patterns.
- [Angular Experts Podcast](https://angularexperts.io/podcasts/) — Angular, NgRx, RxJS, and NX. Hosted by Tomas Trajan and Kevin Kreuzer.
- [Frontside Podcast — RxJS with Ben Lesh and Tracy Lee](https://frontside.com/podcast/091-rx-js-with-ben-lesh-and-tracy-lee/) — Deep dive into the ecosystem.

## The Observable Standard

*The effort to make Observable a native part of JavaScript and the Web Platform.*

| Track | Status | Venue |
|-------|--------|-------|
| [TC39 proposal-observable](https://github.com/tc39/proposal-observable) | Stage 1 (dormant) | ECMAScript / TC39 |
| [WHATWG/WICG Observable](https://github.com/WICG/observable) | Active Draft (Nov 2025) | Web Platform / WHATWG |
| [TC39 proposal-signals](https://github.com/tc39/proposal-signals) | Stage 1 (active) | ECMAScript / TC39 |

The original TC39 Observable proposal was introduced in 2015 by Jafar Husain but has remained at Stage 1. The active development has moved to the **WHATWG/WICG** venue, where Ben Lesh and Dominic Farolino (Google) are championing Observables as a Web Platform API.

**Native Observables have begun shipping!** The Observable API landed in **Chrome 135**, Edge 135+, and other Chromium-based browsers. Firefox and Safari have not yet implemented it. RxJS 8 development was paused specifically to align with this native implementation — future RxJS versions will complement and extend native Observables rather than replace them.

Meanwhile, **Signals** (a separate TC39 proposal) address a different aspect of reactivity — fine-grained, synchronous state tracking — and are complementary to Observables rather than a replacement. Angular has already adopted Signals as a core primitive alongside RxJS.

## Related Reactive Libraries

*The broader reactive programming ecosystem in JavaScript.*

| Library | Description | Author(s) |
|---------|-------------|-----------|
| [most.js](https://github.com/cujojs/most) | Ultra-high performance reactive programming. Consistently the fastest in benchmarks. | Brian Cavalier, David Chase |
| [xstream](https://github.com/staltz/xstream) | An extremely intuitive, small, and fast reactive stream library. Designed for Cycle.js. | André Staltz |
| [Bacon.js](https://github.com/baconjs/bacon.js) | A small FRP library for JavaScript. One of the pioneers of reactive JS. | Juha Paananen |
| [Kefir.js](https://github.com/kefirjs/kefir) | Reactive Programming library inspired by Bacon.js and RxJS with focus on high performance and low memory consumption. | Roman Pominov |
| [Highland.js](https://highlandjs.org/) | Re-thinking the JavaScript utility belt. Manages synchronous and asynchronous code using Node-like Streams. | Caolan McMahon |
| [Wonka](https://github.com/kitten/wonka) | A tiny but capable push & pull stream library for TypeScript and ReasonML. | Phil Pluckthun |
| [Callbags](https://github.com/callbag/callbag) | A lightweight protocol for composable push-pull streams. | André Staltz |

---

## People

*The brilliant humans who built, shaped, and championed the RxJS ecosystem. This project exists because of their vision, dedication, and generosity. Thank you.*

### The Architects

- **[Erik Meijer](https://twitter.com/headinthebox)** — The father of Reactive Extensions. Created Rx at Microsoft, inspiring reactive programming across every major language. A true visionary whose work changed how we think about asynchronous programming.

- **[Ben Lesh](https://twitter.com/BenLesh)** — Lead maintainer of RxJS since version 5. Rewrote the library from scratch, making it faster, more modular, and more debuggable. Now championing the WHATWG Observable proposal to bring Observables natively to the web. Co-founder at This Dot Labs. Has given countless hours to the community through talks, training, and mentorship. Thank you, Ben.

- **[Jafar Husain](https://twitter.com/jhusain)** — Former Technical Lead at Netflix. Pioneered the use of reactive programming for async data at Netflix and brought the Observable proposal to TC39. His work demonstrated that reactive patterns could work at massive scale.

- **[Matt Podwysocki](https://twitter.com/mattpodwysocki)** — One of the earliest and most passionate evangelists for Reactive Extensions in JavaScript. Worked at Microsoft and Netflix helping bring Rx to the web. His energy and advocacy helped build the community from the ground up.

### The Educators

- **[André Staltz](https://twitter.com/andrestaltz)** — Creator of Cycle.js, xstream, and Callbags. Wrote "[The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754)" — the most-shared reactive programming resource ever. Built RxMarbles. Created multiple Egghead courses. André's gift for making complex ideas accessible has introduced hundreds of thousands of developers to reactive programming. Now working at Socket. Thank you, André.

- **[Brian Troncone](https://twitter.com/BTroncone)** — Creator of [Learn RxJS](https://www.learnrxjs.io), one of the most beloved learning resources in the ecosystem. Clear, practical, and always up to date. Countless developers learned RxJS through Brian's examples.

- **[Cédric Soulas](https://twitter.com/cedric_soulas)** — Creator of [Reactive.how](https://reactive.how), the beautiful animated card system for learning reactive operators. A testament to how great design can make complex concepts approachable.

- **[Denis Stoyanov (xgrommx)](https://twitter.com/xgrommx)** — Author of the comprehensive [RxJS Book](https://xgrommx.github.io/rx-book/index.html) and curator of awesome functional programming resources. A tireless contributor to the knowledge base.

### The Builders

- **[Nicholas Jamieson (cartant)](https://github.com/cartant)** — Created an extraordinary number of essential RxJS tools: `eslint-plugin-rxjs`, `rxjs-spy`, `rxjs-marbles`, `rxjs-etc`, and more. Nicholas built the tooling layer that makes RxJS safer and more debuggable in production. The ecosystem owes him an enormous debt.

- **[Michael Hladky](https://twitter.com/Michael_Hladky)** — Creator of rx-angular and founder of Push-Based. Google Developer Expert, Microsoft MVP. A relentless champion of Angular performance and reactivity. His work on `@rx-angular/template` and `@rx-angular/state` has made reactive Angular practical at scale.

- **[Jay Phelps](https://twitter.com/_jayphelps)** — Creator of redux-observable, bringing the power of RxJS to the Redux ecosystem. Made reactive middleware accessible to the massive React/Redux community.

- **[Paul Taylor](https://twitter.com/trxcllnt)** — Co-author of RxJS 5. Ben Lesh said he "wouldn't have been able to ship those first versions without Paul Taylor." Now at NVIDIA/RAPIDS working on Apache Arrow. His explanations of hot vs cold Observables remain some of the clearest ever written.

- **[Daniel Meyer (pubkey)](https://github.com/pubkey)** — Creator of RxDB, the reactive database. Proved that RxJS patterns work beautifully for real-time, offline-first data management.

- **[Brandon Roberts](https://github.com/brandonroberts)** — Lead maintainer of NgRx and creator of AnalogJS (Angular meta-framework). Angular Google Developer Expert. A cornerstone of the Angular reactive ecosystem.

- **[Mike Ryan](https://github.com/MikeRyanDev)** — Co-creator of NgRx. Wrote the initial NgRx Store and Effects code that brought Redux-style reactive state management to Angular. Google Developer Expert.

- **[Alex Okrushko](https://twitter.com/AlexOkrushko)** — NgRx core team member and creator of backoff-rxjs. A driving force in the Angular reactive state management ecosystem.

### The Community Champions

- **[Tracy Lee](https://twitter.com/ladyleet)** — CEO of This Dot Labs. Organized RxJS Live, the world's first RxJS conference. Brought together the community through events, panels, and advocacy. A tireless champion for open source.

- **[Jan-Niklas Wortmann](https://github.com/niklas-wortmann)** — RxJS core team member and Developer Advocate at JetBrains. Angular GDE. Helping shape the future of the library and improving the developer experience through better docs and tooling.

- **[Jason Weinzierl](https://github.com/JasonWeinzierl)** — Took over maintenance of the RxJS ESLint ecosystem with `eslint-plugin-rxjs-x`, ensuring the community has modern linting support for ESLint v9+.

- **[Shai Reznik](https://twitter.com/saborido)** — Creator of observer-spy and HiRez.io. Made testing RxJS Observables dramatically simpler.

- **[Sergi Mansilla](https://twitter.com/paboroso)** — Author of *Reactive Programming with RxJS*. Brought reactive concepts to life through creative examples.

- **[Randall Koutnik](https://twitter.com/rkoutnik)** — Author of *Build Reactive Websites with RxJS*. Senior engineer at Netflix who made reactive web development practical and fun.

- **[Deborah Kurata](https://twitter.com/DeborahKurata)** — Google Developer Expert. Her ng-conf talks on RxJS pipelines and reactive Angular components have guided thousands of developers toward better reactive patterns.

- **[OJ Kwon](https://github.com/nicknisi)** — One of the most prolific code contributors to the RxJS repository. Quietly essential to the project's health.

- **[Dominic Farolino](https://github.com/nicknisi)** — Google engineer and editor of the WICG Observable spec. Working alongside Ben Lesh to bring native Observables to browsers.

### And You

The RxJS ecosystem thrives because of every developer who has filed an issue, submitted a PR, answered a Stack Overflow question, written a blog post, given a talk, or helped a colleague understand Observables. If you've contributed to this ecosystem in any way — **thank you**.

---

## Contribute

Contributions welcome! Read the [contribution guidelines](contributing.md) first.

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.
