import java.awt.*;
import javax.swing.*;

public class DoomLikeGame extends JFrame {
    private static final int MAP_WIDTH = 10;
    private static final int MAP_HEIGHT = 10;
    private static final int PLAYER_START_X = 5;
    private static final int PLAYER_START_Y = 5;
    private static final int PLAYER_SIZE = 20;
    private static final int TILE_SIZE = 50;

    private int[][] map;
    private int playerX;
    private int playerY;

    public DoomLikeGame() {
        setTitle("Doom-like Game");
        setSize(800, 600);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);

        // Initialize map
        map = new int[MAP_WIDTH][MAP_HEIGHT];
        initializeMap();

        // Initialize player position
        playerX = PLAYER_START_X;
        playerY = PLAYER_START_Y;

        // Set up the game canvas
        Canvas canvas = new Canvas();
        canvas.setPreferredSize(new Dimension(800, 600));
        canvas.setFocusable(false);

        add(canvas);
        pack();
        setVisible(true);
    }

    private void initializeMap() {
        // Fill the map with random values for demonstration
        for (int i = 0; i < MAP_WIDTH; i++) {
            for (int j = 0; j < MAP_HEIGHT; j++) {
                map[i][j] = Math.random() > 0.8 ? 1 : 0; // 1 represents walls, 0 represents empty space
            }
        }
    }

    @Override
    public void paint(Graphics g) {
        super.paint(g);

        // Draw the map
        for (int i = 0; i < MAP_WIDT




