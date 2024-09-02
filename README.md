# CommandCraft

CommandCraft is a powerful command-handling library for PocketMine-MP plugins. It provides an intuitive API for defining commands, managing arguments, and handling subcommands. With CommandCraft, you can create flexible and efficient commands for your Minecraft Bedrock server.

## Features

- **Easy Command Creation**: Define commands with minimal boilerplate code.
- **Argument Handling**: Support for built-in and custom argument types.
- **Subcommands**: Organize complex commands with subcommands.
- **Asynchronous Execution**: Run commands asynchronously to avoid server lag.
- **Permissions**: Restrict command access based on player permissions.
- **Dynamic Commands**: Create commands that adapt based on runtime conditions.

## Installation

### Using Composer

1. Add CommandCraft to your `composer.json`:

    ```json
    {
        "require": {
            "kanadeblue/commandcraft": "^1.0"
        }
    }
    ```

2. Run `composer install` to install the library.

### Manual Installation

1. Download the CommandCraft library.
2. Include the library in your project's `src/` directory.

## Usage

### Basic Command

Create a simple `/greet` command that sends a greeting message to the player.

```php
use CommandCraft\CommandBuilder;

$greetCommand = CommandBuilder::create("greet", "Greet a player")
    ->handler(function ($context) {
        $sender = $context->getSender();
        $senderName = $sender->getName();
        $sender->sendMessage("Hello, $senderName!");
    })
    ->build();

$commandHandler->register($greetCommand);
```
