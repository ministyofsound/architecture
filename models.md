## Data Models

### `User`

- `uid` - `String`
- `email` - `String`
- `subscribedPodcasts` - `Array<Ref<Podcast>>`
- `subscribedCategories` - `Array<Ref<Category>>`
- `bookmarkedEpisodes` - `Array<Ref<Episode>>`
- `favoriteEpisodes` - `Array<Ref<Episode>>`
- `playingQueue` - `Ref<PlayingQueue>`
- `playlists` - `Array<Ref<Playlist>>`
- `listeningHistory` - `Ref<ListeningHistory>`

### `Play`

- `episode` - `Ref<Episode>`
- `playPosition` - `Number` - the current play position of the episode
- `completed` - `boolean`
- `listen` - `Ref<Listen>`

### `Listen`

- `updatedAt` - `String`
- `createdAt` - `String`

### `ListeningHistory`

- `createdAt` - `String`
- `updatedAt` - `String`
- `listens` - `Array<Ref<Listen>>`

### `PlayingQueue`

- `plays` - `Array<Ref<Play>>`
- `createdAt` - `String`
- `updatedAt` - `String`

### `Playlist`

- `title` - `String`
- `description` - `String`
- `tags` - `JSONB` - An array of tags
- `episodes` - `Array<Ref<Episode>>`

### `Podcast`

- `title` - `String`
- `description` - `String`
- `feedUrl` - `String`
- `generator` - `String`
- `url` / `link` - `String`
- `image` - `String`
- `explicit` - `String`
- `summary` - `String`
- `language` - `String`
- `publisher` - `Ref<Publisher>`
- `palette` - `JSONB`
- `entities` - `Array<Ref<Entity>>`
- `categories` - `Array<Ref<Category>>`
- `episodes` - `Ref<Array<Episode>>`

### `Episode`

- `title` - `String`
- `subTitle` - `String`
- `summary` - `String`
- `author` - `Ref<Author>`
- `content` - `String` - A description of the podcast episode as a html string
- `contentSnippet` - A shorter description of the podcast episode
- `length` - `Number` - the length of the podcast episode in milliseconds
- `encoding` - `enum MP3 | WAV`
- `source` - `String` - Defined as `url` in the data - this is the audio source url for the episode
- `link` - `String` - the link to the podcast url
- `guid` - `String`
- `publicationDate` - `String`
- `explicit` - `boolean`
- `episodeType` - `enum Full | Bonus | Trailer`
- `image` - `String`
- `season` - `Number`
- `episodeNo` - `Number`
- `entities` - `Array<Ref<Entity>>`

### `Publisher`

- `name` - `String`
- `email` - `String`

### `Category`

- `name` - `String`

### `Entity`

- `entityType` - `String`
- `title` - `String`