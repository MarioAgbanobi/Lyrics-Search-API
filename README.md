# Lyrics.ovh API Javascript Project
This project is a javascript library for interacting with the Lyrics.ovh API. With this library, you can easily search for lyrics for any song, artist, or album.

# Installation
To use this library, you will need to obtain an API key from Lyrics.ovh. You can sign up for a free account at https://lyrics.ovh/api.

Once you have your API key, you can install the library via npm by running the following command:

<pre><code> const apiURL = 'https://api.lyrics.ovh'; </code></pre>

<pre><code> 
//get lyrics
async function getLyrics(artist, songTitle){
    //alert(songTitle, artist)

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
