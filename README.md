# ASINCRONISMO-DOM

LABORATORIO 05: INTRODUCCIÓN A JAVASCRIPT

## 🚀 Desarrallo 

Pagina web de referencia: SPOTIFY (https://open.spotify.com/intl-es)

### Ejercicio

// CALLBACK: Funcion que se ejecuta dentro de otra funcion

const getSpotifyUser = () => {
    console.log({id: "1", name: "UsuarioSpotify", plan: "Premium"});
}

setTimeout(getSpotifyUser, 3000); // Simulamos un callback que se ejecuta después de 3 segundos.


// PROMESAS

const fetchSpotifyData = (endpoint) => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            // Simulación: Si el endpoint es correcto, resuelve la promesa, si no, la rechaza
            endpoint === "playlist" ? resolve("Playlist fetched successfully!") : reject("Failed to fetch playlist");
        }, 2000);
    });
}

// Then y Catch

fetchSpotifyData("playlist")
    .then((response) => console.log(response))
    .catch((error) => console.log(error));
    
//Async - await

const getSpotifyPlaylist = async () => {
    try {
        let playlist = await fetchSpotifyData("playlist");
        console.log(playlist); 
    } catch (error) {
        console.log(error); 
    }
}
getSpotifyPlaylist();

//Uso fetch

const SPOTIFY_TOKEN = "d792c41f92d1437085c9e8824db79000";
const SPOTIFY_URL = "https://open.spotify.com/intl-es";

// Fetch a la API de Spotify para obtener la canción que se está reproduciendo
fetch(SPOTIFY_URL, {
    method: "GET",
    headers: {
        Authorization: `Bearer ${SPOTIFY_TOKEN}`
    }
})
    .then((response) => response.json())
    .then((data) => console.log(data))  // Manejo de la respuesta de la API
    .catch((error) => console.log(error));  // Manejo de errores

## Author

👤 **Autor**

- GitHub: [@Jonathan02jr](https://github.com/jonathan02jr)
