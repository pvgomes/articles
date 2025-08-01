+++
date = '2025-05-01T12:06:27+02:00'
draft = false
title = 'Macos Using Port 5000 Butnolocal Env 2025 05 17'
+++
![](https://miro.medium.com/v2/resize:fit:700/0*wFYzGBS_RC924Bl-)

Photo by [Szabo Viktor](https://unsplash.com/@vmxhu?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com/?utm_source=medium&utm_medium=referral)

If you’ve ever encountered the error message `EADDRINUSE: address already in use 0.0.0.0:5000` while running `npm run dev` on macOS, you’re not alone. This issue often arises when macOS's built-in AirPlay feature is occupying the port you need for your development server.

# What’s Happening?

In macOS Monterey and later versions, Apple introduced a feature called **AirPlay Receiver**. This feature allows your Mac to receive AirPlay streams from other Apple devices (like iPhones, iPads, etc.). To facilitate this, macOS listens on port 5000 (along with port 7000) for incoming connections, which conflicts with local development servers that also default to using port 5000.

# How to Solve the Problem

Fortunately, the solution is straightforward. By disabling the AirPlay Receiver feature, you can free up port 5000 for your development work.

Here’s how to fix it:

**Open System Settings**:

* *   Click the **Apple logo** in the top-left corner of your screen.
* *   Select **System Settings**.
* *   **Go to AirPlay Settings**:
* *   In macOS Ventura and later:
* *   Navigate to **General** \> **AirDrop & Handoff**.
* *   Find the **AirPlay Receiver** option.
* *   **Disable AirPlay Receiver**:
* *   Toggle off or uncheck the **AirPlay Receiver** option.

By doing this, you stop the **ControlCenter** process from listening on port 5000, and the port becomes available for your development server.

# Confirm the Fix

After disabling AirPlay Receiver, you can check if port 5000 is free by running the following command in your terminal:

sudo lsof -iTCP:5000 -sTCP:LISTEN

If there’s no output, the port is free and you can now run your development server without issues.

# Alternatives

If you don’t want to disable AirPlay Receiver, consider changing your development server’s port to another available one (e.g., 5001). Most frameworks like Flask and React allow you to specify a different port in the configuration.

# Conclusion

The issue of port 5000 being in use on macOS is tied to the AirPlay Receiver feature, which listens on the same port for AirPlay connections. By disabling AirPlay Receiver in your system settings, you can easily free up the port for your development work.