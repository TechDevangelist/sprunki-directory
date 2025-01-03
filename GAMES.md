# Game Data Structure

Games are defined in the `_data/games.yml` file with the following structure:

```yaml
- title: Game Title
  screenshot: /path/to/screenshot.png
  iframe_url: https://game.url
  description: Short description of the game
  tags: [tag1, tag2]
```

## Required Fields
- `title`: Display name of the game
- `screenshot`: Path to the game screenshot
- `iframe_url`: URL of the game to embed

## Optional Fields
- `description`: Short description of the game
- `tags`: Array of tags for categorization

## Example
```yaml
- title: Space Adventure
  screenshot: /assets/images/space.png
  iframe_url: https://spacegame.com
  description: Explore the galaxy in this space adventure
  tags: [space, adventure]
```