# Qvio Teams 2.0 - User Guide

**Version 2.0 Release**

---

## What's New in Qvio 2.0

Qvio 2.0 introduces **Teams**, a powerful collaboration feature that transforms how you work with video content. This guide will help you understand the new team-based experience and how it differs from the previous individual user model.

---

## Understanding the Change: From Individual to Team-Based

### Before Teams (v1.x)

- All content was tied to individual user accounts
- Videos, folders, and subscriptions belonged to a single user
- Collaboration was limited to sharing links
- Billing was managed per individual account

### With Teams (v2.0)

- Content is now organized within **Teams**
- Multiple users can collaborate on the same videos
- Role-based permissions control who can do what
- Billing is managed at the team level
- Real-time awareness of who's editing content

**Important:** When you first log in after the upgrade, a default team called "My Team" has been automatically created for you. All your existing videos, folders, and subscription have been migrated to this team. You don't need to do anything - your content is safe and accessible!

---

## Getting Started with Teams

### Your Default Team

Upon logging in for the first time after the 2.0 update:

1. A team called **"My Team"** has been created automatically
2. You are the **Owner** of this team
3. All your existing content is now part of this team
4. Your subscription has been transferred to this team

### The Team Switcher

Located in the top navigation bar (click the team avatar), the **Team Switcher** allows you to:

- View all teams you belong to
- Search for teams by name
- Switch between teams instantly
- View pending invitations (when you have pending invites)
- Navigate to the Team Dashboard to manage all your teams

Click the team avatar in the header to open the switcher dropdown.

---

## Team Roles and Permissions

Qvio uses a four-tier role system to manage access and capabilities within each team:

| Role       | Description                | Key Capabilities                                                         |
| ---------- | -------------------------- | ------------------------------------------------------------------------ |
| **Owner**  | Full control over the team | All permissions + billing management, ownership transfer, team deletion  |
| **Admin**  | Team management access     | Invite/remove members, change roles, edit branding, force-unlock content |
| **Editor** | Content creation access    | Create and edit videos, manage folders, view team info                   |
| **Viewer** | Read-only access           | View videos, cannot edit or manage team                                  |

### Permission Details

| Action               | Owner | Admin | Editor | Viewer |
| -------------------- | ----- | ----- | ------ | ------ |
| View videos          | Yes   | Yes   | Yes    | Yes    |
| Create/edit videos   | Yes   | Yes   | Yes    | No     |
| Delete videos        | Yes   | Yes   | Yes    | No     |
| Manage folders       | Yes   | Yes   | Yes    | No     |
| Invite members       | Yes   | Yes   | No     | No     |
| Remove members       | Yes   | Yes   | No     | No     |
| Change member roles  | Yes   | Yes   | No     | No     |
| Edit team branding   | Yes   | Yes   | No     | No     |
| Force-unlock content | Yes   | Yes   | No     | No     |
| Manage billing       | Yes   | No    | No     | No     |
| Transfer ownership   | Yes   | No    | No     | No     |
| Delete team          | Yes   | No    | No     | No     |

---

## Team Management

### Creating a New Team

1. Navigate to the **Team Dashboard** (click "Manage Teams" in the Team Switcher, or go to `/teams/dashboard`)
2. Click the **"Create Team"** button
3. **Step 1 - Select Plan**: Choose your team's subscription tier
4. **Step 2 - Team Details**: Enter your team information:
   - **Team Name** (required): A URL-friendly identifier (3-100 characters, letters, numbers, underscores, and hyphens only)
   - **Display Name** (required): The human-readable name shown throughout the app
   - **Description** (optional): A brief description of your team
5. Click **Create**

You will automatically become the **Owner** of the new team. Logo and banner images can be added later in Settings.

### Editing Team Settings

**Owners and Admins** can customize team settings:

1. Navigate to your team's overview page (click on the team from the Team Dashboard)
2. Select the **Settings** tab
3. From here you can edit:
   - **Team Name**: The display name shown throughout the app
   - **Team Handle**: The URL-friendly identifier (letters, numbers, underscores, hyphens only)
   - **Description**: A brief description of your team
   - **Logo**: Upload a team logo (SVG or PNG, max 10MB)
   - **Banner**: Upload a banner image (JPG or PNG, max 10MB)

Changes are **auto-saved** as you type - you'll see a "Saving..." indicator followed by "Saved" when complete.

### Deleting a Team

**Owners only** can delete a team:

1. Go to the **Settings** tab
2. Scroll to the **Danger Zone** section
3. Click **Delete Team**
4. Type the team name to confirm
5. Click **Confirm Delete**

**Warning:** Deleted teams enter a 90-day recovery period, after which all content is permanently removed.

---

## Team Overview Page

When you select a team from the Team Dashboard, you'll see the **Team Overview** page with multiple tabs. The tabs visible depend on your role and the team's subscription tier.

### Available Tabs

| Tab               | Visibility                            | Purpose                                                                    |
| ----------------- | ------------------------------------- | -------------------------------------------------------------------------- |
| **Overview**      | All members                           | View team info, logo, banner, handle, public URL, and your role            |
| **Members**       | All members                           | View and manage team members (hidden for single-seat plans)                |
| **Invitations**   | Owners & Admins                       | Send invitations and manage pending invites (hidden for single-seat plans) |
| **Notifications** | Members with notification permissions | Configure team notification preferences                                    |
| **Subscription**  | Owners                                | View plan details, usage, and manage billing                               |
| **Settings**      | Owners & Admins                       | Edit team details, branding, and danger zone actions                       |

### Overview Tab

The Overview tab displays:

- Team name and description
- Team logo and banner images
- Team handle (the URL-friendly identifier)
- Public profile URL with copy button
- Your current role in the team

### Members Tab

The Members tab shows a list of all team members with:

- Name and email
- Role (with dropdown to change roles for Owners/Admins)
- Join date
- Actions (remove member, transfer ownership)

### Invitations Tab

The Invitations tab allows Owners and Admins to:

- View all pending invitations
- Send new invitations
- Revoke pending invitations
- See seat usage (e.g., "5 / 10 seats used")

### Subscription Tab

The Subscription tab (Owners only) displays:

- Current plan name and status
- Usage metrics (video minutes, Q&As)
- Seat allocation
- **Upgrade** button to change plans
- **Manage Subscription** button to access the Stripe billing portal

---

## Team Membership

### Inviting Members

**Owners and Admins** can invite new team members:

1. Go to your team's overview page
2. Select the **Invitations** tab
3. Click **Invite People**
4. Enter email addresses (you can enter multiple emails separated by commas or new lines)
5. Select the role for all invitees (Viewer, Editor, or Admin)
6. Click **Send Invite**

The invitees will receive an email with instructions to join the team. The modal shows a permissions matrix so you can see what each role can do.

**Note:** If your team has a seat limit, you'll see the current usage (e.g., "5 / 10 seats used"). You cannot invite more members than your available seats.

### Accepting Invitations

When you receive a team invitation:

1. Check your email for the invitation
2. Click the link to log in or sign up
3. You should be redirected to the invitation acceptance page
4. Should you not be, navigate to **Pending Invitations** (shown in your notifications or team switcher)
5. Click **Accept** or **Reject** for each invitation

### Managing Members

**Owners and Admins** can manage existing members:

- **Change Role**: Click the role dropdown next to a member's name to change their role
- **Remove Member**: Click the remove icon next to a member to remove them from the team

### Transferring Ownership

**Owners only** can transfer ownership to another member. There are two ways:

**From the Settings Tab:**

1. Go to the **Settings** tab
2. Scroll to the **Danger Zone** section
3. Click **Transfer Ownership**
4. Select the member to transfer ownership to
5. Type the confirmation text
6. Click **Confirm Transfer**

**From the Members Tab:**

1. Go to the **Members** tab
2. Find the member you want to transfer ownership to
3. Click the transfer ownership action
4. Confirm the transfer

After transfer, you become an Admin of the team.

---

## Working with Team Content

### Understanding Content Ownership

- All videos and folders now belong to the **team**, not individual users
- When you create content, it's automatically associated with your currently active team
- Use the Team Switcher to ensure you're working in the correct team before creating content

**Important:** Videos cannot be moved between teams. Make sure you're in the correct team before creating new content.

### Content Locking (Collision Prevention)

When multiple team members can edit the same content, Qvio prevents conflicts with **automatic content locking**:

#### How It Works

1. When you open a video for editing, it's automatically **locked** to you
2. Other team members see a banner: _"Locked by [your name] since [time]"_
3. Others can view the video in **read-only mode** while you're editing
4. The lock automatically releases when you:
   - Close the editor
   - Stay inactive for 10 minutes

#### Lock Indicators

- **In the editor**: A banner shows the current lock status
- **In video lists**: A lock icon appears on locked videos

#### Force Unlock (Admins and Owners)

If content is locked by someone who left or forgot to close the editor:

1. **Admins** and **Owners** can click the **Force Unlock** button
2. This releases the lock immediately
3. The original editor loses their lock and cannot save further changes

#### Lock Conflict Dialog

When you try to edit a video that's already locked, you'll see a **Lock Conflict** dialog with these options:

- **Cancel**: Close the dialog and return to the video list
- **Open Read-Only**: View the video without editing capabilities
- **Force Unlock** (Admins/Owners only): Take over the lock from the current editor

The dialog shows who currently holds the lock and when they acquired it.

---

## Billing and Subscriptions

### Team-Based Billing

Subscriptions are now managed at the **team level**:

- Each team has its own subscription
- The **Owner** manages billing and payments
- All team members benefit from the team's subscription tier

### Viewing Billing Information

1. Go to your team's overview page
2. Select the **Subscription** tab (Owners only)
3. View current plan, usage metrics, and seat allocation
4. Click **Manage Subscription** to access the Stripe billing portal for payment details and history

### What Happens When a Subscription Expires

If a team's subscription expires or payment fails:

- All team members immediately lose access to premium features
- Content remains accessible in read-only mode (depending on feature tier)
- The Owner must update payment information to restore access

---

## Analytics

### Team-Scoped Analytics

Analytics are now aggregated at the **team level**:

- **Dashboard Overview**: See total views, engagement, and performance for all team videos
- **Video Analytics**: Individual video performance metrics
- **Q&A Analytics**: Questions and answers from your team's videos

### Accessing Analytics

1. Go to your team dashboard
2. Select **Analytics** from the navigation
3. Filter by date range, video, or other parameters

All analytics now show data for the entire team's content, not just individual users.

---

## Frequently Asked Questions

### General Questions

**Q: What happened to my existing videos and folders?**
A: They've been automatically migrated to your default "My Team" and remain fully accessible.

**Q: Can I still use Qvio without creating a team?**
A: Everyone now works within teams. Your default "My Team" functions exactly like your individual account did before - you're just the sole owner.

**Q: Can I be a member of multiple teams?**
A: Yes! You can create teams, be invited to teams, and switch between them using the Team Switcher.

### Team Management

**Q: What's the difference between an Admin and Owner?**
A: The Owner has full control including billing management, ownership transfer, and team deletion. Each team has exactly one Owner. Admins can manage members and content but cannot access billing or delete the team.

**Q: Can I transfer videos between teams?**
A: No, videos are permanently associated with the team where they were created. Plan ahead when creating new content.

**Q: What happens to team content if the Owner leaves?**
A: The Owner must transfer ownership to another member before leaving. A team cannot exist without an Owner.

### Invitations

**Q: Can I resend an invitation?**
A: Yes, you can revoke the existing invitation and send a new one.

**Q: Do invitations expire?**
A: No, invitations remain valid until they are accepted, rejected, or revoked.

**Q: What if I invite someone who doesn't have a Qvio account?**
A: They'll receive an email with a sign-up link. Once they create an account, they can accept the invitation.

### Content Locking

**Q: How long can I hold a lock on content?**
A: Locks are maintained as long as you're actively editing. After 10 minutes of inactivity, the lock automatically releases.

**Q: What if someone leaves their editor open and blocks everyone?**
A: Owners and Admins can use the **Force Unlock** feature to release stale locks.

---

## Quick Reference

### Common Workflows

**Invite a Colleague:**
Team Switcher > Manage Teams > Select Team > Invitations Tab > Invite People

**Switch Teams:**
Click Team Avatar (top nav) > Select desired team

**Check Who's Editing:**
Video List > Look for lock badge > Hover for time details

**Update Team Branding:**
Team Overview > Settings Tab > Upload Logo/Banner

**View Your Invitations:**
Team Switcher > View Invites (when you have pending invitations)

**Manage Billing:**
Team Overview > Subscription Tab > Manage Subscription

---

## Need Help?

If you have questions or encounter issues with the new Teams feature:

- **In-App Help**: Click the help icon in the navigation
- **Support**: Contact support@hia.ai

---

_This guide covers Qvio version 2.0. Features and interfaces may change in future updates._
