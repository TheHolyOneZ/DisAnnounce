# DisAnnounce
DisAnnounce is a powerful multi-server announcement system for Discord that allows server administrators to create, schedule, and distribute announcements across multiple servers. This extension enables server owners to establish announcement networks where servers can subscribe to each other's announcement channels.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# DisAnnounce Extension Documentation

## Overview
DisAnnounce is a powerful multi-server announcement system for Discord that allows server administrators to create, schedule, and distribute announcements across multiple servers. This extension enables server owners to establish announcement networks where servers can subscribe to each other's announcement channels.

## Key Features
- **Cross-Server Announcements**: Send announcements to multiple servers simultaneously
- **Announcement Scheduling**: Schedule announcements for future dates and times
- **Rich Formatting**: Customize announcements with titles, colors, images, and thumbnails
- **Templates**: Save and reuse announcement templates
- **Subscription System**: Servers can subscribe to announcement channels from other servers
- **Centralized Management**: Manage all your scheduled announcements from one place

## Command Reference

### Basic Commands

#### `!disannounce`
Shows the main help menu with available commands.

#### `!disannounce create`
Opens an interactive announcement creator with buttons to customize various aspects of your announcement.
- Must be used in a registered announcement channel
- Requires Administrator permission

#### `!disannounce register [channel]`
Registers a channel as an announcement source that other servers can subscribe to.
- If no channel is specified, the current channel is used
- Requires Administrator permission
- Provides server and channel IDs that other servers need to subscribe

#### `!disannounce unregister`
Unregisters your server's announcement channel.
- Requires Administrator permission
- All subscriptions to this channel will no longer receive announcements

#### `!disannounce subscribe <server_id> <channel_id> [channel]`
Subscribes to announcements from another server's announcement channel.
- `server_id`: The ID of the server with the announcement channel
- `channel_id`: The ID of the announcement channel to subscribe to
- `channel`: Optional - The channel where you want to receive announcements (defaults to current channel)
- Requires Administrator permission

#### `!disannounce unsubscribe [server_id] [channel_id]`
Unsubscribes from announcements.
- If no parameters are provided, unsubscribes from all announcement channels
- If server_id and channel_id are provided, unsubscribes from that specific channel
- Requires Administrator permission

#### `!disannounce scheduled`
Shows a list of all scheduled announcements for your server with options to:
- View announcement details
- Cancel scheduled announcements
- Navigate through pages of scheduled announcements
- Requires Manage Channels permission

### Advanced Commands

#### `!disannounce list`
Lists all available announcement channels that you can subscribe to.
- Shows server name, channel name, and subscription status
- Requires Manage Channels permission

#### `!disannounce status`
Shows your current DisAnnounce configuration:
- Your registered announcement channel (if any)
- Number of servers subscribed to your announcements
- Channels you're subscribed to
- Template status
- Subscription channel
- Requires Manage Channels permission

#### `!disannounce template`
Shows template management commands.
- Requires Administrator permission

#### `!disannounce template create`
Opens an interactive template creator.
- Similar to the announcement creator but saves settings for future announcements
- Requires Administrator permission

#### `!disannounce template view`
Shows your current announcement template.
- Requires Administrator permission

#### `!disannounce template delete`
Deletes your current announcement template.
- Requires Administrator permission

## Announcement Creator Features
When using `!disannounce create` or `!disannounce template create`, you'll have access to these customization options:

- **Set Title**: Set the announcement title (up to 256 characters)
- **Set Content**: Set the main announcement content (up to 4000 characters)
- **Set Color**: Set the color of the announcement embed using hex color codes
- **Set Image**: Add a large image to the announcement using a URL
- **Set Thumbnail**: Add a small thumbnail image to the announcement using a URL
- **Schedule**: Schedule the announcement for a future date and time
- **Send Now**: Send the announcement immediately to all subscribed servers
- **Save Template**: Save the current settings as a template for future announcements
- **Cancel**: Cancel creating the announcement

## Setup Guide

1. **Register an Announcement Channel**:
   ```
   !disannounce register #announcements
   ```

2. **Share Your Channel Information**:
   After registering, you'll receive your server ID and channel ID that other servers need to subscribe.

3. **Subscribe to Other Servers**:
   ```
   !disannounce subscribe 123456789012345678 987654321098765432 #incoming-announcements
   ```

4. **Create and Send Announcements**:
   Go to your registered channel and use `!disannounce create` to make announcements.

5. **Check Your Status**:
   ```
   !disannounce status
   ```

## Best Practices

1. **Use Templates**: Create templates for consistent announcement styling.
2. **Schedule Important Announcements**: Use the scheduling feature for important announcements to ensure timing is perfect.
3. **Organize Subscriptions**: Consider creating dedicated channels for incoming announcements from different sources.
4. **Regular Maintenance**: Use `!disannounce scheduled` to manage your upcoming announcements.
5. **Permission Control**: Only give announcement creation permissions to trusted staff members.

## Technical Notes

- Announcements are stored in JSON configuration files
- Scheduled announcements are checked every minute
- Templates and subscriptions persist through bot restarts
- All announcement data is stored locally on the bot's host machine

This extension is part of ZygnalBot by TheHolyOneZ and provides a comprehensive solution for managing announcements across multiple Discord servers.
