---
title: Managing Chronograf organizations
menu:
  chronograf_1_4:
    name: Managing Chronograf organizations
    weight: 40
    parent: Administration
---

**On this page:**

* [About Chronograf organizations](#about-chronograf-organizations)
* [Using the default organization](#using-the-default-organization)
* [Configuring the default organization](#configuring-the-default-organization)
* [Creating organizations](#creating-organizations)
* [Removing organizations](#removing-organizations)


## About Chronograf organizations

> ***Note:*** Support for organizations and individual users (rather than the shared user) is new in Chronograf 1.4.
>
> For information about the new user roles and SuperAdmin status, see [Managing Chronograf users](/chronograf/v1.4/administration/managing-chronograf-users/).

A Chronograf organization is a collection of Chronograf users who share common Chronograf-owned resources, including dashboards, InfluxDB and Kapacitor connections, and alerts. Organizations can be used to represent companies, functional units, projects, or teams. Chronograf users can be members of multiple organizations.

## Using the Default organization

>***Note:*** This default organization can be used to support Chronograf as configured in versions earlier than 1.4.

Upon installation, the Default organization is ready for use and can be used as-is for many purposes. This Chronograf instance includes the following behaviors:

* Anyone who can open the application in a web browser can use it.
* All users are members with SuperAdmin status.
* Authentication is not required unless OAuth 2.0 authentication is configured.

## Creating organizations

**Required status:** SuperAdmin

Upon installation Chronograf includes the Default organization, ready to be used as-is for many purposes.

Additional organizations can be created by SuperAdmin users to support the requirements of your company, organizational units, teams, and projects.

**To create an organization:**

1) In the navigation bar of the Chronograf application, click **Admin** (crown icon) > **Chronograf** to open the **Chronograf Admin** page.
2) Click the **Organizations** tab and then click **Create Organization**.
3) Under **Name**, click on **"Untitled Organization"** and enter the new organization name.
4) Under **Default Role**, select the default role for new users. Valid options include `member` (default), `viewer`, `editor`, and `admin`.
5) Click **Save**.

## Configuring organizations

**Required status:** SuperAdmin

You can configure existing and new organizations in the **Organizations** tab of the **Chronograf Admin** page as follows:

* **Name**: The name of the organization. Click on the organization name to change it.

  > ***Note:*** You can change the Default organization's name, but that organization will always be the default organization.

* **Public**: [Default organization only] Indicates whether a user can authenticate without being explicitly added to the organization. When **Public** is toggled to **Off**, new users cannot authenticate into your Chronograf instance unless they have been explicitly added to the organization by an administrator.

  > ***Note:*** All organizations other than the Default organization require users to be explicitly added by an administrator.

* **Default Role**: The role granted to new users by default. Valid options are `member` (default), `viewer`, `editor`, and `admin`.
* **Config**: **All new users are SuperAdmins**: Enabled by default, toggling this to **Off** any new users must be explicitly granted SuperAdmin status.

JWT and OAuth 2.0 authentication providers are functional components of the Chronograf security model

Related information:

* [Managing Chronograf users](/chronograf/v1.4/administration/managing-chronograf-users/)
* [Managing InfluxDB users](/chronograf/v1.4/administration/managing-influxdb-users/)
* [Managing security](/chronograf/v1.4/administration/managing-security/)

## Removing organizations

**Required status:** SuperAdmin

When an organization is removed:

* Users within that organization are removed and no longer authorized and will be logged out of the application.
* All users with roles in that organization are updated to no longer have a role in that organization
* All resources specific to that organization are deleted.


**To remove an organization:**

1) In the navigation bar of the Chronograf application, select **Admin** ("crown" icon) > **Chronograf** to open the **Chronograf Admin** page.
2) Click the **Organizations** tab to view a list of organizations.
3) To the right of the the organization that you want to remove, click the **Remove** button (trashcan icon) and then confirm by clicking the **Save** button.