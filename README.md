// Handle player moves
buttons[i][j].addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        if (board[row][col] == ' ' && currentPlayer == 'X') {
            board[row][col] = currentPlayer;
            buttons[row][col].setText(Character.toString(currentPlayer));
            if (checkWin(currentPlayer)) {
                JOptionPane.showMessageDialog(null, currentPlayer + " wins!");
                resetBoard();
            } else if (checkDraw()) {
                JOptionPane.showMessageDialog(null, "Game is a draw!");
                resetBoard();
            } else {
                currentPlayer = 'O';
                aiMakeMove();
            }
        }
    }
});
