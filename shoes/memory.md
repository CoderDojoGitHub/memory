
Today we're going to build a memory game. We're going to do this using Shoes, which uses the Ruby programming language.


### Prereqs - Installing Shoes and a text editor


#### Windows

On windows, download and unzip **Shoes 3 +video for Windows**
* [http://github.com/downloads/shoes/shoes/shoes3.exe.zip](http://github.com/downloads/shoes/shoes/shoes3.exe.zip)

Download and install **Notepad++**
* [http://download.tuxfamily.org/notepadplus/6.1.3/npp.6.1.3.Installer.exe](http://download.tuxfamily.org/notepadplus/6.1.3/npp.6.1.3.Installer.exe)

#### Mac OSX

On Mac OSX 10.6 (Snow Leopard) and 10.7 (Lion), download **Shoes 3**.
Open the dmg file, and copy the Shoes app to your computer.
* https://github.com/downloads/shoes/shoes/shoes-3.1.0.dmg

Download and open **Text Wrangler**
* http://ash.barebones.com/TextWrangler_4.0.1.dmg


### Running your first Shoes program

Start by opening your text editor (TextWrangler on a Mac, or Notepad++ on
Windows).

Start a new file, and save it as "memory.rb".

Now type the following code that tells Shoes to make a window:

	Shoes.app :width => 800, :height => 600 do
	end

Save the file. And now we're ready to run it!

Run the Shoes program that you downloaded earlier. You should see "Welcome to
Shoes". Click on "Open an App." Now find paint.rb that you saved earlier and
open it. You should see your 800x600 window appear.


### Placing the cards

In our game of 'memory', we're going to have a board of 12 cards.
We'll do 4 columns and 3 rows. So if we want 4 columns of cards,
that means they can be at most `800 / 4` (== 200) wide. And
that's only if they're touching! So to give them a little margin,
let's say that they're 100 wide with a 50px border on the sides.

So to draw your first row of cards, type this in your text editor:

```
Shoes.app :width => 800, :height => 600 do
  blue = "#0000FF"

  4.times do |column|
    rect 200 * column + 50, 50, 100, 100, :fill => blue
  end
end
```

Go ahead and run your program in Shoes again, and you should see
a single row of blue square cards.

Next, lets fill out the board by putting in additional rows.
Just like we drew rectangles 4 times for each column in the row,
now we want to draw that row 3 times. Let's make our cards similarly
spaced, with 50px margins on the top.

```
Shoes.app :width => 800, :height => 600 do
  blue = "#0000FF"

  4.times do |column|
    3.times do |row|
      rect 200 * column + 50, 200 * row + 50, 100, 100, :fill => blue
    end
  end

end
```
