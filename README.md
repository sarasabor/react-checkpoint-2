# react-checkpoint-2

Voici les étapes pour construire une application de cartes de joueurs FIFA avec React en utilisant create-react-app et react-bootstrap.

Étape1 : Créer un nouveau projet avec create-react-app
Dans votre terminal, exécutez la commande suivante :

bashnpx create-react-app fifa-player-cardscd fifa-player-cards

Étape2 : Créer le fichier players.js
Créez un fichier appelé players.js dans le dossier src qui contiendra un tableau d'objets JSON avec les détails des joueurs.

javascript//
 {  
 name: "Lionel Messi",  
 team: "Inter Miami",  
 nationality: "Argentin",  
 jerseyNumber:10,  
 age:36,  
 imageUrl: "https://upload.wikimedia.org/wikipedia/commons/a/a8/Lionel_Messi_20180626.jpg"  
 },  
 {  
 name: "Cristiano Ronaldo",  
 team: "Al Nassr",  
 nationality: "Portugais",  
 jerseyNumber:7,  
 age:38,  
 imageUrl: "https://upload.wikimedia.org/wikipedia/commons/8/8c/Cristiano_Ronaldo_2018.jpg"  
 },  
 {  
 name: "Kylian Mbappé",  
 team: "Paris SG",  
 nationality: "Français",  
 jerseyNumber:7,  
 age:24,  
 imageUrl: "https://upload.wikimedia.org/wikipedia/commons/0/03/Kylian_Mbapp%C3%A9_2018.jpg"  
 },  
 {  
 name: "Kevin De Bruyne",  
 team: "Manchester City",  
 nationality: "Belge",  
 jerseyNumber:17,  
 age:32,  
 imageUrl: "https://upload.wikimedia.org/wikipedia/commons/5/5b/Kevin_De_Bruyne_2018.jpg"  
 }  
];  

export default players;  
Étape3 : Créer le composant Player.js
Créez un fichier appelé Player.js dans le dossier src.

jsx//
import { Card } from 'react-bootstrap';  

const Player = ({ name, team, nationality, jerseyNumber, age, imageUrl }) => {  
 return (  
 <Card style={{ width: '18rem', margin: '1rem' }}>  
 <Card.Img variant="top" src={imageUrl} />  
 <Card.Body>  
 <Card.Title>{name}</Card.Title>  
 <Card.Text>  
 Équipe: {team} <br />  
 Nationalité: {nationality} <br />  
 Numéro de maillot: {jerseyNumber} <br />  
 Âge: {age} ans </Card.Text>  
 </Card.Body>  
 </Card>  
 );  
};  

Player.defaultProps = {  
 name: "Inconnu",  
 team: "Inconnu",  
 nationality: "Inconnue",  
 jerseyNumber: "Inconnu",  
 age: "Inconnu",  
 imageUrl: "https://via.placeholder.com/150"  
};  

export default Player;  
Étape4 : Créer le composant PlayersList.js
Créez un fichier appelé PlayersList.js dans le dossier src.

jsx//
import players from './players';  
import Player from './Player';  

const PlayersList = () => {  
 return (  
 <div style={{ display: 'flex', flexWrap: 'wrap', justifyContent: 'center' }}>  
 {players.map((player, index) => (  
 <Player key={index} {...player} />  
 ))}  
 </div>  
 );  
};  

export default PlayersList;  
Étape5 : Importer et utiliser PlayersList dans App.js
Modifiez le fichier App.js pour inclure et afficher la liste des joueurs.

jsx//
import 'bootstrap/dist/css/bootstrap.min.css';  
import PlayersList from './PlayersList';  

function App() {  
 return (  
 <div className="App">  
 <h1 style={{ textAlign: 'center', margin: '20px' }}>FIFA Player Cards</h1>  
 <PlayersList />  
 </div>  
 );  
}  

export default App;  
Étape6 : Exécuter l'applicationAprès avoir mis en place tout cela, vous pouvez démarrer votre application :
bashnpm start

RésuméAvec ces étapes, vous avez créé une application React qui affiche des cartes de joueurs FIFA avec des détails tels que le nom, l'équipe, la nationalité, le numéro de maillot, l'âge et une image. Chaque joueur est affiché en utilisant des cartes de react-bootstrap, et vous avez implémenté des valeurs par défaut pour les propriétés.N'hésitez pas à personnaliser le style ou à ajouter des fonctionnalités pour améliorer votre application !
