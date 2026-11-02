# Temporary GitHub Pages domain test

This disposable repository tests whether a Pages project in SunshineStream is automatically served beneath LizardByte's existing app.lizardbyte.dev domain.

The gh-pages branch root is published with no CNAME. Existing production domain ownership, DNS, and repository redirects were left intact.

## Result

Verified November 1, 2026, after the [successful initial deployment](https://github.com/SunshineStream/pages-domain-test-20261101/actions/runs/41383897030) of commit d35d76e2720bc7ff23a2686b452ada2df1a785af.

| URL | HTTP result | Test marker |
| --- | --- | --- |
| https://sunshinestream.github.io/pages-domain-test-20261101/ | 200 HTML | Present |
| https://sunshinestream.github.io/pages-domain-test-20261101/probe.json | 200 JSON | Present |
| https://app.lizardbyte.dev/pages-domain-test-20261101/ | 404 HTML | Absent |
| https://app.lizardbyte.dev/pages-domain-test-20261101/probe.json | 404 HTML | Absent |

The test shows that a project in SunshineStream does not automatically inherit the custom domain of LizardByte's organization site. Preserving the existing umbrella paths would need a separate publishing or routing arrangement. GitHub documents domain inheritance for project sites owned by the same account: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages#using-a-custom-domain-across-multiple-repositories

The production site root, /Sunshine/, and /ThemerrDB/deployment.json all returned 200 with unchanged SHA-256 body hashes compared with the pre-test baseline. The production Pages configuration still assigns app.lizardbyte.dev to LizardByte/LizardByte.github.io. SunshineStream/Sunshine still resolves to LizardByte/Sunshine, repository ID 438803890.

No attempt was made to reassign the production custom domain to this test repo.

The repository and Pages site are retained for inspection and can be removed after the results have been reviewed.