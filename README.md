# Vencord Voice Channel Admin Plugin

This plugin automatically blocks users when they join your voice channel by simulating button clicks on bot messages.

## Features

- Listens for voice state updates in a configured server
- Automatically triggers the "block_button" action when users join your voice channel
- Anti-flood protection to prevent duplicate actions
- Configurable server ID and bot ID
- Easy enable/disable toggle

## Configuration

- **Target Server ID**: The Discord server ID where your voice channel is located (default: 500074231544152074)
- **Bot ID**: The ID of the bot that sends the voice channel management messages (default: 1279925176422633522)
- **Enabled**: Toggle to enable/disable the automatic blocking feature

## Settings

- **Server ID**: The Discord server ID where your voice channel is located
- **Bot ID**: Bot ID that sends the voice channel management message
- **Enable**: Enable automatic blocking when users join your voice channel

## How it works

1. The plugin listens for `VOICE_STATE_UPDATES` events
2. When a user joins your voice channel in the configured server, it:
   - Finds the voice channel's associated text channel
   - Locates the first message from the configured bot
   - Finds the "block_button" component in that message
   - Simulates clicking that button to block the user

## Anti-flood Protection

The plugin includes anti-flood protection that prevents the same user from being processed multiple times in quick succession.

## Requirements

- You must be in a voice channel in the configured server
- The bot must have sent a message with the "block_button" component in the voice channel's text chat
- You must have the necessary permissions to block users in that server

## Installation

1. Copy the `blu-vc-channeladmin` folder to your Vencord `src/userplugins` directory
2. Rebuild Vencord: `npm run build`
3. Restart Discord
4. Enable the plugin in Vencord settings

## AI Disclaimer

This plugin was developed with the assistance of AI (Claude Sonnet 4). The AI helped with code structure, implementation details, and debugging. While the code has been reviewed and tested, please use it at your own discretion. If you encounter any issues, please report them through the GitHub issues page.
