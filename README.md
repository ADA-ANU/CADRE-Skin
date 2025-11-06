# Coordinated Access for Data, Researchers and Environments (CADRE) Skin

This repository contains the CSS file used to style (skin) the CADRE authentication page at [https://cilogon.aaf.edu.au/authorize](https://cilogon.aaf.edu.au/authorize) with CADRE branding.

> [!NOTE]
> The terms 'skin' (the stylesheet) and 'skinning' (applying the style) are used by Australian Access Federation (AAF) and CiLogon.

## Applying the Skin

A copy of this CSS is saved within each CiLogon instance (Dev, Test, Prod). The skin's styling is dynamically inserted into the `<head>` element of the login page when a user is directed there.

> [!TIP]
> CiLogon determines which skin to apply using a combination of query parameters, with the highest priority being:
> 
> 1. `clientid` query parameter: If the `clientid` is associated with CADRE's CO (Collaborative Organization), the skin is applied automatically.
> 2. `skin` query parameter: If a skin isn't associated with the `clientid`, the `skin` parameter can be used. For CADRE, this is `?skin=cadre`.
> 3. Default CiLogon CSS
>
> _Example: [https://cilogon.aaf.edu.au?skin=cadre](https://cilogon.aaf.edu.au?skin=cadre)_


As can be seen from the screenshot below, when inspecting the HTML of the page we can see the `<style>` tag where the CADRE skin is being inserted.

![Inspecting the Inserted Skin Styling](docs-images/viewing-skin-styling.png)

## Updating the Skin

Since a copy of the skin is saved on CiLogon instances, updates require notifying a member of the AAF or CiLogon team.

- After changes are merged into this repository, the AAF/CiLogon team downloads the latest CSS to update their Dev, Test, and Production instances.
- Changes are typically tested on Dev and Test environments first before going to Production.

## Developing & Testing Changes

The simplest way to test is to copy your updated CSS content and paste it directly into the `<style>` tag within the `<head>` element of the live page using your browser's developer tools.

For more extensive changes, consider hosting the CSS file locally and linking to it externally to reflect changes faster.

Always test your styling changes on the following CiLogon pages (substituting dev for test or prod as needed):

- https://dev.cilogon.aaf.edu.au/?skin=cadre
- https://dev.cilogon.aaf.edu.au/me/?skin=cadre
- https://dev.cilogon.aaf.edu.au/device/?skin=cadre
- https://dev.cilogon.aaf.edu.au/authorize?scope=org.cilogon.userinfo+openid+profile+email&response_type=code&redirect_uri=https%3A%2F%2Fdemo-dev.cilogon.aaf.edu.au%2Fcilogon2%2Fready&prompt=login&client_id=cilogon%3Adev.cilogon.aaf.edu.au%2Fdemo&skin=cadre

Once you confirm the styling is correct, update the repository and notify the CiLogon/AAF team.