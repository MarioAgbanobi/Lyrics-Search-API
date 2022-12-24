# Lyrics.ovh API Javascript Project
This project is a javascript library for interacting with the Lyrics.ovh API. With this library, you can easily search for lyrics for any song, artist, or album.

![1](https://user-images.githubusercontent.com/72680556/209419646-e303baa3-723c-4cb0-875c-2e96a0222a94.png)

# Installation
To use this library, you will need to obtain an API key from Lyrics.ovh. You can sign up for a free account at https://lyrics.ovh/api.

Once you have your API key, you can install the library via npm by running the following command:

<pre><code> const apiURL = 'https://api.lyrics.ovh'; </code></pre>

# Each lyrics object contains the following properties:

title: The title of the song
artist: The artist of the song
lyrics: The lyrics of the song
You can also use the getLyrics method to retrieve lyrics for a specific song, artist, and album. This method takes three arguments: song, artist, and album, and returns a promise that resolves to a lyrics object.
<pre><code> 
async function getLyrics(artist, songTitle){

    const res = await fetch(`${apiURL}/v1/${artist}/${songTitle}`);
    const data = await res.json();

    const lyrics = data.lyrics.replace(/(\r\n|\r|\n)/g, '<br>');

    result.innerHTML = 
    `<h2>
    <strong>
        ${artist}
    </strong> -  ${songTitle}
    - 
    <p>${lyrics}</p>
    </h2>
    `
}
</code></pre>

# Limitations
Please note that the Lyrics.ovh API has rate limits in place, so you should be mindful of how often you make requests. You can find more information about the rate limits and usage restrictions at https://lyrics.ovh.
