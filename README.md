# PRODIGY_CS_04

Task 4 : Task-04 Simple Keylogger

PROBLEM STATEMENT : Create a basic keylogger program that records and logs keystrokes. 
Focus on logging the keys pressed and saving them to a file. 
Note: Ethical considerations and permissions are crucial for projects involving keyloggers.

VIDEO LINK = > https://imagekit.io/tools/asset-public-link?detail=%7B%22name%22%3A%22blackbox%20-%20task4%20-%20Visual%20Studio%20Code%202025-01-10%2000-46-26.mp4%22%2C%22type%22%3A%22video%2Fmp4%22%2C%22signedurl_expire%22%3A%222028-01-09T19%3A55%3A38.248Z%22%2C%22signedUrl%22%3A%22https%3A%2F%2Fmedia-hosting.imagekit.io%2F%2F326c2bf3e4d24e7d%2Fblackbox%2520-%2520task4%2520-%2520Visual%2520Studio%2520Code%25202025-01-10%252000-46-26.mp4%3FExpires%3D1831060538%26Key-Pair-Id%3DK2ZIVPTIP2VGHC%26Signature%3DeXu2XorEhaGcXwucazbdS7X3We6fEu9VBeRJN8vz7HwXLeS9mu~2r2P9gguuzzvbzPRNmp1kxCwBBaVpZlJbCVhrHaCSr62ztZTCtam7nXA9pIAy66rEqeipkHCo9QsWpCN35j6oRaNdRdzKEcp6CVpGA2yjMEWLYty5-~G19laJLIh2ZXmAKy22TH1ZKsYDnidgpcc7wUTZA39qtP8Nj9SxQD98n3vS0~dsazKyVtJHa93UjKHGwkAuHdVb4nSFn0XaD6ECcN16RjadQx3sYTVACyGqfaoLaYITEg~BjVp9uvAEtHWfpSeuv65RuCPd6pnhMNnQ0GwMkMPFX8yPFg__%22%7D

How the Keylogger Works:

A keylogger is a program that records all the keystrokes (keyboard inputs) made by a user. In this task, we will build a basic keylogger that listens for and logs every key pressed, and stores that information in a file. Let's break down the key components of how a basic keylogger works:

1. Keylogger Initialization

    The keylogger program is initiated when executed. It begins running in the background silently and does not interfere with the user’s normal activities.
    The program is designed to stay active, continuously listening for keystrokes until the user stops it manually (or it’s stopped programmatically).

2. Listening for Keystrokes

    The core functionality of the keylogger is to listen for keypress events. This can be achieved by using libraries such as pynput or keyboard in Python.
    When you run the program, it enters into a listening state, monitoring all key presses on the keyboard. It detects each individual keypress as soon as a user interacts with the keyboard.

Example: If the user presses "A", "1", or even "Shift", the keylogger detects these events.

3. Capturing Keystrokes

   Normal Keys: When a regular key (alphabetic, numeric, or a standard punctuation mark) is pressed, the keylogger captures the key.
        For example, pressing "A" would be captured as key.char (the character "A").

    Special Keys: Keys such as Shift, Ctrl, Alt, Enter, or Esc are treated as special keys. These keys do not have a direct "character" associated with them, so the program logs them using their names.
        For example, pressing the Shift key would be captured as key (which would be logged as Key.shift).

5. Logging the Keystrokes

    Every time a key is pressed, the keylogger writes the keypress to a log file. The file can be stored on the user's system in a hidden or designated folder.
    The log typically includes the keypress itself, and in some cases, the timestamp of when the key was pressed. The program records the event in real-time as the keys are typed.

6. Running in the Background

    Once the keylogger is started, it operates in the background, listening for keypresses continuously.
    It doesn’t show up on the user interface and doesn’t provide any notification, which makes it nearly invisible to the user. However, it’s constantly monitoring the keyboard for activity.
    The keylogger will keep running until it’s explicitly stopped (e.g., by terminating the program or pressing a special key like Esc).

7. Saving to a Log File

    The keystrokes, once captured, are written to a log file (e.g., keylog.txt). This file stores all the user input during the keylogger’s running time.
    Each keystroke is logged along with a timestamp (if configured), so you can track the sequence and timing of each action.

8. Stopping the Keylogger

    The keylogger can be terminated based on certain conditions. For example, the program can be designed to stop when a specific key (such as Escape) is pressed.
    Alternatively, it can be manually stopped by the user, or it can be designed to run persistently until the system is restarted or shut down.

Ethical Considerations:

  A keylogger captures sensitive information such as passwords, usernames, credit card numbers, and other private data. As such, it is crucial to use a keylogger only for legitimate, ethical purposes and with the explicit consent of the user.
  
  Unauthorized use of keyloggers is illegal and considered a violation of privacy. Always ensure that keyloggers are used only in ethical contexts, such as for security testing with consent, or in educational settings where all parties are informed.

Keylogger Code Overview (Explained):

In the basic keylogger program, we use the pynput library to monitor key events:

  Setting up the Listener:
        The Listener listens for key press and release events.
        It can detect when a key is pressed (on_press) or released (on_release).

  Logging Keystrokes:
        When a key is pressed, the on_press() function is triggered, which logs the key to a file.
        Special keys (like Shift or Ctrl) are logged as their names (e.g., Key.shift), while regular keys are logged as characters (e.g., A).

  Stopping the Listener:
        The keylogger can listen for the Esc key press to stop the program gracefully.
