// ============================================================
// SAFARI DETECTION & DELAY CONFIGURATION
// Platform: All devices
// ============================================================
const isSafari = /^((?!chrome|android).)*safari/i.test(navigator.userAgent),
    safariDelay = isSafari ? 150 : 0;

// ============================================================
// GSAP PLUGIN REGISTRATION
// Platform: All devices
// ============================================================
document.addEventListener("DOMContentLoaded", () => {
    void 0 !== window.gsap
        ? gsap.registerPlugin(ScrollTrigger, SplitText)
        : document.documentElement.classList.add("gsap-not-found");
}),

    // ============================================================
    // MOCKUP WRAP 3D TILT ANIMATION
    // Platform: Desktop (mousemove) + Mobile (scroll-based)
    // Desktop: Interactive 3D tilt effect following mouse movement
    // Mobile: Scroll-triggered 3D rotation animation
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        const e = document.querySelector(".mockup_wrap");
        if (!e) return;
        const t = 15;
        if (
            ((e.style.transformStyle = "preserve-3d"),
                (e.style.webkitTransformStyle = "preserve-3d"),
                (e.style.willChange = "transform"),
                (e.style.webkitBackfaceVisibility = "hidden"),
                (e.style.backfaceVisibility = "hidden"),
                (e.parentElement.style.perspective = "1000px"),
                (e.parentElement.style.webkitPerspective = "1000px"),
                window.matchMedia("(pointer: fine)").matches)
        )
            window.addEventListener("mousemove", (o) => {
                const a = (o.clientX / window.innerWidth) * 2 - 1,
                    i = (o.clientY / window.innerHeight) * 2 - 1;
                gsap.to(e, {
                    rotationY: a * t,
                    rotationX: -i * t,
                    ease: "power2.out",
                    duration: 0.6,
                    transformPerspective: 1e3,
                });
            }),
                window.addEventListener("mouseleave", () => {
                    gsap.to(e, { rotationX: 0, rotationY: 0, z: 0, duration: 1, ease: "power3.out" });
                });
        else {
            gsap.timeline({
                scrollTrigger: {
                    trigger: '[data-animation-trigger="image-split"]',
                    start: "top 80%",
                    end: "bottom top",
                    scrub: 1,
                },
            })
                .to(e, { rotationX: -15, rotationY: t, ease: "none", transformPerspective: 1e3 })
                .to(e, { rotationX: t, rotationY: -15, ease: "none", transformPerspective: 1e3 })
                .to(e, { rotationX: 0, rotationY: 0, ease: "none", transformPerspective: 1e3 });
        }
    }),

    // ============================================================
    // CHART ANIMATION
    // Platform: All devices
    // Animates chart bars, numbers, and line on scroll
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        const e = document.querySelector(".chart_trigger");
        e &&
            (gsap.set(".chart_bar", { scaleY: 0, transformOrigin: "bottom center" }),
                gsap.set(".chart_number", { opacity: 0 }),
                gsap.set(".chart_line", { strokeDashoffset: 1e4, strokeDasharray: 1e4 }),
                gsap.to(".chart_bar", {
                    scaleY: 1,
                    ease: "power2.out",
                    scrollTrigger: {
                        trigger: e,
                        start: "10% top",
                        end: "bottom bottom",
                        scrub: !0,
                        onUpdate: (e) => {
                            gsap.to(".chart_number", { opacity: e.progress, overwrite: "auto", duration: 0.1 });
                        },
                    },
                }),
                gsap.to(".chart_line", {
                    strokeDashoffset: 8330,
                    ease: "power2.out",
                    scrollTrigger: { trigger: e, start: "20% top", end: "bottom bottom", scrub: !0 },
                }));
    }),

    // ============================================================
    // TESTIMONIALS WRAPPER ANIMATION
    // Platform: Mobile only (max-width: 35em / 560px)
    // Fade-in and slide-up animation for testimonial grid items
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(max-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="testimonials-wrapper"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelectorAll(".u-grid > *");
                            o.length && t.from(o, { opacity: 0, y: 50, duration: 0.8, stagger: 0.2 }, 0.8);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // NAVIGATION ANIMATION
    // Platform: All devices
    // Fade-in and slide-up animation for logo elements
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        document.fonts.ready.then(() => {
            setTimeout(() => {
                const e = document.querySelectorAll('[data-animation-trigger="nav"]');
                e.length &&
                    e.forEach((e) => {
                        (e.style.visibility = "visible"), e.offsetHeight;
                        const t = gsap.timeline({
                            scrollTrigger: { trigger: e, start: "top 85%", once: !0 },
                            defaults: { ease: "power2.out" },
                        }),
                            o = e.querySelectorAll(".logo_element");
                        o.length && t.from(o, { opacity: 0, yPercent: 50, duration: 1.2 }, 0);
                    });
            }, safariDelay);
        });
    }),

    // ============================================================
    // HERO SECTION ANIMATION
    // Platform: All devices
    // Animates background, heading, paragraph, and buttons
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        document.fonts.ready.then(() => {
            setTimeout(() => {
                const e = document.querySelectorAll('[data-animation-trigger="hero"]');
                e.length &&
                    e.forEach((e) => {
                        (e.style.visibility = "visible"), e.offsetHeight;
                        const t = gsap.timeline({
                            scrollTrigger: { trigger: e, start: "top 85%", once: !0 },
                            defaults: { ease: "power2.out" },
                        }),
                            o = e.querySelectorAll(".u-background-slot");
                        o.length && t.to(o, { duration: 2, scale: 1 }, 0);
                        const a = e.querySelector(".u-heading > *");
                        a && t.from(a, { opacity: 0, y: 30, duration: 0.8 }, 0.3);
                        const i = e.querySelector('[data-animate="true"] p');
                        i && t.from(i, { opacity: 0, y: 30, duration: 0.8 }, 0);
                        const r = e.querySelectorAll(".u-button-wrapper > * > *");
                        r.length && t.from(r, { opacity: 0, yPercent: 50, duration: 0.8, stagger: 0.2 }, 0.8);
                    });
            }, safariDelay);
        });
    }),

    // ============================================================
    // STACKED CONTENT ANIMATION - DESKTOP
    // Platform: Desktop only (min-width: 35em / 560px)
    // Text split animation with heading, paragraph, buttons, grid/accordion
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(min-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="stacked-content"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 85%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelector(".u-heading > *");
                            if (o) {
                                (o.style.webkitFontSmoothing = "antialiased"),
                                    (o.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(o, {
                                    type: "chars,lines,words",
                                    linesClass: "split-line",
                                    wordsClass: "split-word",
                                    charsClass: "split-char",
                                });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                            }
                            const a = e.querySelector('[data-animate="true"] p');
                            if (a) {
                                (a.style.webkitFontSmoothing = "antialiased"),
                                    (a.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(
                                        e.lines,
                                        { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.18 },
                                        0.5
                                    );
                            }
                            const i = e.querySelectorAll(".u-button-wrapper > * > *");
                            i.length && t.from(i, { opacity: 0, yPercent: 50, duration: 0.8, stagger: 0.2 }, 0.6);
                            const r = e.querySelectorAll(".u-grid > *, .accordion_list > *");
                            r.length && t.from(r, { opacity: 0, y: 30, duration: 0.8, stagger: 0.2 }, 0.6);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // STACKED CONTENT ANIMATION - MOBILE
    // Platform: Mobile only (max-width: 35em / 560px)
    // Text split animation with heading, paragraph, and buttons (no grid)
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(max-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="stacked-content"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelector(".u-heading > *");
                            if (o) {
                                (o.style.webkitFontSmoothing = "antialiased"),
                                    (o.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(o, {
                                    type: "chars,lines,words",
                                    linesClass: "split-line",
                                    wordsClass: "split-word",
                                    charsClass: "split-char",
                                });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                            }
                            const a = e.querySelector('[data-animate="true"] p');
                            if (a) {
                                (a.style.webkitFontSmoothing = "antialiased"),
                                    (a.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(
                                        e.lines,
                                        { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.18 },
                                        0.5
                                    );
                            }
                            const i = e.querySelectorAll(".u-button-wrapper > * > *");
                            i.length && t.from(i, { opacity: 0, yPercent: 50, duration: 0.8, stagger: 0.2 }, 0.8);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // GRID ANIMATION - MOBILE
    // Platform: Mobile only (max-width: 35em / 560px)
    // Animates card, accordion, and chart elements in grids
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(max-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll(".u-grid");
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelectorAll(
                                    ".u-grid > .card_primary_wrap, .accordion_list > *, .chart_wrap"
                                );
                            o.length && t.from(o, { opacity: 0, y: 30, duration: 0.8, stagger: 0.2 }, 0.2);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // IMAGE SPLIT ANIMATION - DESKTOP
    // Platform: Desktop only (min-width: 35em / 560px)
    // Text split with heading, paragraphs, images, and buttons
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(min-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="image-split"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 70%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelector(".u-heading > *");
                            if (o) {
                                (o.style.webkitFontSmoothing = "antialiased"),
                                    (o.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(o, {
                                    type: "chars,lines,words",
                                    linesClass: "split-line",
                                    wordsClass: "split-word",
                                    charsClass: "split-char",
                                });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                            }
                            const a = e.querySelectorAll('[data-animate="true"] p');
                            if (a.length) {
                                a.forEach((e) => {
                                    (e.style.webkitFontSmoothing = "antialiased"),
                                        (e.style.webkitTransform = "translateZ(0)");
                                });
                                const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(
                                        e.lines,
                                        { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.18 },
                                        0.25
                                    );
                            }
                            const i = e.querySelectorAll("[data-image-wrap]");
                            i.length && t.from(i, { opacity: 0, y: 30, stagger: 0.2, duration: 0.8 }, 0.5);
                            const r = e.querySelectorAll(".u-button-wrapper > * > *");
                            r.length && t.from(r, { opacity: 0, yPercent: 50, duration: 0.8, stagger: 0.2 }, 0.8);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // IMAGE SPLIT ANIMATION - MOBILE
    // Platform: Mobile only (max-width: 35em / 560px)
    // Text split with heading, paragraphs, images, and buttons
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(max-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="image-split"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelector(".u-heading > *");
                            if (o) {
                                (o.style.webkitFontSmoothing = "antialiased"),
                                    (o.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(o, {
                                    type: "chars,lines,words",
                                    linesClass: "split-line",
                                    wordsClass: "split-word",
                                    charsClass: "split-char",
                                });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                            }
                            const a = e.querySelectorAll('[data-animate="true"] p');
                            if (a.length) {
                                a.forEach((e) => {
                                    (e.style.webkitFontSmoothing = "antialiased"),
                                        (e.style.webkitTransform = "translateZ(0)");
                                });
                                const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(
                                        e.lines,
                                        { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.18 },
                                        0.25
                                    );
                            }
                            const i = e.querySelectorAll("[data-image-wrap]");
                            i.length && t.from(i, { opacity: 0, y: 30, duration: 0.8 }, 0.5);
                            const r = e.querySelectorAll(".u-button-wrapper > * > *");
                            r.length && t.from(r, { opacity: 0, yPercent: 50, duration: 0.8, stagger: 0.2 }, 0.6);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // ABOUT SECTION ANIMATION - DESKTOP
    // Platform: Desktop only (min-width: 35em / 560px)
    // Text split with heading, paragraphs, images, and text content
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(min-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll('[data-animation-trigger="about"]');
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 70%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelector(".u-heading > *");
                            if (o) {
                                (o.style.webkitFontSmoothing = "antialiased"),
                                    (o.style.webkitTransform = "translateZ(0)");
                                const e = new SplitText(o, {
                                    type: "chars,lines,words",
                                    linesClass: "split-line",
                                    wordsClass: "split-word",
                                    charsClass: "split-char",
                                });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                            }
                            const a = e.querySelectorAll('[data-animate="true"] p');
                            if (a.length) {
                                a.forEach((e) => {
                                    (e.style.webkitFontSmoothing = "antialiased"),
                                        (e.style.webkitTransform = "translateZ(0)");
                                });
                                const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                                e.lines.forEach((e) => {
                                    (e.style.display = "block"), (e.style.overflow = "hidden");
                                }),
                                    t.from(
                                        e.lines,
                                        { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.18 },
                                        0.25
                                    );
                            }
                            const i = e.querySelectorAll(".u-image-wrapper");
                            i.length && t.from(i, { opacity: 0, y: 30, stagger: 0.2, duration: 0.8 }, 0.5);
                            const r = e.querySelectorAll(".u-text p");
                            r.length && t.from(r, { opacity: 0, y: 30, stagger: 0.2, duration: 0.8 }, 0.5);
                        });
                }, safariDelay);
            });
    }),

    // ============================================================
    // ABOUT SECTION ANIMATION - MOBILE
    // Platform: Mobile only (max-width: 35em / 560px)
    // Text split with heading, paragraphs, and text content
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
    window.matchMedia("(max-width: 35em)").matches &&
        document.fonts.ready.then(() => {
            setTimeout(() => {
                const e = document.querySelectorAll('[data-animation-trigger="about"]');
                e.length &&
                    e.forEach((e) => {
                        (e.style.visibility = "visible"), e.offsetHeight;
                        const t = gsap.timeline({
                            scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                            defaults: { ease: "power2.out" },
                        }),
                            o = e.querySelector(".u-heading > *");
                        if (o) {
                            (o.style.webkitFontSmoothing = "antialiased"),
                                (o.style.webkitTransform = "translateZ(0)");
                            const e = new SplitText(o, {
                                type: "chars,lines,words",
                                linesClass: "split-line",
                                wordsClass: "split-word",
                                charsClass: "split-char",
                            });
                            e.lines.forEach((e) => {
                                (e.style.display = "block"), (e.style.overflow = "hidden");
                            }),
                                t.from(e.lines, { opacity: 0, yPercent: 100, duration: 0.8, stagger: 0.2 }, 0);
                        }
                        const a = e.querySelectorAll('[data-animate="true"] p');
                        if (a.length) {
                            a.forEach((e) => {
                                (e.style.webkitFontSmoothing = "antialiased"),
                                    (e.style.webkitTransform = "translateZ(0)");
                            });
                            const e = new SplitText(a, { type: "lines", linesClass: "split-line" });
                            e.lines.forEach((e) => {
                                (e.style.display = "block"), (e.style.overflow = "hidden");
                            }),
                                t.from(
                                    e.lines,
                                    { opacity: 0, yPercent: 80, duration: 0.8, stagger: 0.05 },
                                    0  // Changed from default (sequential) to 0
                                );
                        }
                        const i = e.querySelectorAll(".u-text p");
                        i.length && t.from(i, { opacity: 0, y: 30, stagger: 0.2, duration: 0.8 }, 0);  // Changed from 0.2 to 0
                    });
            }, safariDelay);
        });
});

    // ============================================================
    // IMAGE WRAPPER ANIMATION - MOBILE
    // Platform: Mobile only (max-width: 35em / 560px)
    // Fade-in and slide-up animation for standalone image wrappers
    // ============================================================
    document.addEventListener("DOMContentLoaded", () => {
        window.matchMedia("(max-width: 35em)").matches &&
            document.fonts.ready.then(() => {
                setTimeout(() => {
                    const e = document.querySelectorAll("[data-image-wrap]");
                    e.length &&
                        e.forEach((e) => {
                            (e.style.visibility = "visible"), e.offsetHeight;
                            const t = gsap.timeline({
                                scrollTrigger: { trigger: e, start: "top 80%", once: !0 },
                                defaults: { ease: "power2.out" },
                            }),
                                o = e.querySelectorAll(".u-image-wrapper");
                            o.length && t.from(o, { opacity: 0, y: 30, stagger: 0.2, duration: 0.8 }, 0.5);
                        });
                }, safariDelay);
            });
    });
