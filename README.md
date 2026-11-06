# Temporary GitHub Pages domain test

This disposable repository records two checks: automatic inheritance of LizardByte's existing Pages hostname and an explicitly configured SunshineStream project subdomain.

## Custom subdomain test

Verified November 5, 2026, with this repository publishing from the gh-pages branch root. Its Pages custom domain and CNAME file both specify sunshine.lizardbyte.dev. GitHub reports verified domain protection, an approved certificate for that hostname, and HTTPS enforcement enabled.

| DNS host | Type | Target |
| --- | --- | --- |
| sunshine.lizardbyte.dev | CNAME | sunshinestream.github.io |

| URL | Result | Test marker |
| --- | --- | --- |
| https://sunshine.lizardbyte.dev/ | 200 HTML with validated TLS | Present |
| https://sunshine.lizardbyte.dev/probe.json | 200 JSON with validated TLS | Present |
| http://sunshine.lizardbyte.dev/ | Redirects to HTTPS, then 200 HTML | Present |
| http://sunshine.lizardbyte.dev/probe.json | Redirects to HTTPS, then 200 JSON | Present |

The marker is sunshinestream-pages-domain-test-20261101-01a18004. The HTML and JSON body hashes match the original native Pages deployment. Production app.lizardbyte.dev, /Sunshine/, and /ThemerrDB/deployment.json returned 200 with unchanged body hashes compared with the baseline taken before this custom-domain test.

This proves that a repository in SunshineStream can serve a dedicated subdomain of lizardbyte.dev. Preserving existing app.lizardbyte.dev project paths still requires separate publishing or routing. The temporary repository is deliberately not named Sunshine, preserving the existing repository redirect.

## Initial inheritance test

Verified November 1, 2026, after the [successful initial deployment](https://github.com/SunshineStream/pages-domain-test-20261101/actions/runs/41383897030) of commit d35d76e2720bc7ff23a2686b452ada2df1a785af. At that time the gh-pages branch root was published with no CNAME, and existing production domain ownership, DNS, and repository redirects were left intact.

| URL at the time of the initial test | HTTP result | Test marker |
| --- | --- | --- |
| https://sunshinestream.github.io/pages-domain-test-20261101/ | 200 HTML | Present |
| https://sunshinestream.github.io/pages-domain-test-20261101/probe.json | 200 JSON | Present |
| https://app.lizardbyte.dev/pages-domain-test-20261101/ | 404 HTML | Absent |
| https://app.lizardbyte.dev/pages-domain-test-20261101/probe.json | 404 HTML | Absent |

That test checked automatic inheritance, without configuring cross-organization publishing or routing. GitHub documents domain inheritance for project sites owned by the same account: [Pages domain inheritance](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages#using-a-custom-domain-across-multiple-repositories).

The native Pages URLs in the historical table now redirect to the configured custom domain. The production Pages configuration remains assigned to LizardByte/LizardByte.github.io. SunshineStream/Sunshine still resolves to LizardByte/Sunshine, repository ID 438803890.

The repository and Pages site are retained for inspection and can be removed after the results have been reviewed.
