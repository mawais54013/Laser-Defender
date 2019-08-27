# Laser-Defender
 
 This is a Laser Defender game built Unity and C# code. All assets are from Kenny.nl and is a single level game to see how high a score each player gets. 

 Objective: Defeat as many ships to gain more points. Small ships are worth 100 points and the large red ships are worth 450 points. 

Preview below:

 ![index](game.gif)

 # Getting Started

 This game is not a mobile game so as keyboard is required, mostly designed for desk monitors and laptops. This game has 3 scenes: Start menu, game scene, and a game over menu. Each enemy ship has their own setup with different display, lasers, and movement throughout the game. All the code is performed in C# for the functionality and the layout is with unity. 

 ## Prerequisites
 Game can only be played on monitor or laptops. 

 # Built With
 - Unity
 - C# 
 - Kenny Assets
 - TextMeshPro
 - DaFonts
 - Particle System
 
# Feature Layout

The code below is a object oriented design that shows what each function is suppose to do when called on during an action on unity. The IEnumerator along with the StartCororutine lets the game wait 2 seconds before going to the game over screen to have the player view the score and the action they were eliminated at. The scene manager is called to load new scenes of the game. 
```
public class Level : MonoBehaviour
{
    [SerializeField] float delayInSeconds = 2f;

    public void LoadStartMenu()
    {
        SceneManager.LoadScene("Start Menu");
    }

    public void LoadGame()
    {
        SceneManager.LoadScene("Game");
        FindObjectOfType<GameSession>().resetGame();
    }

    public void LoadGameOver()
    {
        StartCoroutine(WaitAndLoad());       
    }

    IEnumerator WaitAndLoad()
    {
        yield return new WaitForSeconds(delayInSeconds);
        SceneManager.LoadScene("Game Over");
    }

    public void QuitGame()
    {
        Application.Quit();
    }
}

```

# Author
* **Muhammad** - https://github.com/mawais54013
