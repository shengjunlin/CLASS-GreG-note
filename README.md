# CLASS/GREG-note
CLASS: Continuum and Line Analysis Single-dish Softwares

GreG: Grenoble Graphic

## Interacting with the shell
    $ SHELL_Command [-Opts] [Args]

## Document ##
<code>help</code> Show the list of availavle languages and commands.  
<code>help Lang\\</code> Show the list of availavle commands.  
<code>help [Lang\\]Command [Subtopic]</code> Show the help for this command.  
<code>help [run] TaskName</code> Show the help for this task.  
<code>help go ProcName</code> / <code>input ProcName</code> Show the help for this procedure.  
<code>input ?</code> Show the list of availavle procedures.  

### SIC\ Command Language Summary ###
Basic programming language of CLASS and GreG.

    help sic\
* accept        : Read variable in various format.                                                                                                                 
* begin         : Begin a sub-procedure, help file or data file.
* **break**         : Exit without error from a FOR-NEXT loop.
* compute       : Execute non-arithmetic operations on variables.
* **continue**      : Resume macro or loop execution after PAUSE.
* datetime      : Convert date and/or time to/from various formats.
* define Type V : Define new variables.
* delete        : Delete variables or symbols.
* edit \[File]   : Edit a file or a dump of the Stack.
* **else \[IF Log]** : Alternate IF block directive.
* **end**           : End IF block structure or a sub-procedure.
* execute       : Execute a command line
* **examine Var**   : Type the current value of the specified variable.
* **exit**          : Exit from the program.
* **for \[/while]**  : Open a FOR-NEXT loop.
* **help XX\[\\]**    : Give an explanation of command XX or language XX\.
* **if Logical**    : Start a conditional IF block.
* import Package: Dynamically import another package in current one.
* **let \[/where]**  : Assign value to variable.
* message       : Send a message to screen and/or message file.
* mfit A=F(B,p) : Fit a formula into SIC variables.
* *modify*        : Modify the spectroscopic axis of a cube.
* **next**          : End FOR loop definition and activates the execution.
* on error comm : Change the current error recovery action.
* **pause**         : Set a break point in a Loop or a Macro.
* python        : Start/End intercommunication between SIC and PYTHON.
* **quit**          : Abort an execution interrupted by PAUSE.
* recall \[Text] : Recall line from stack, and edit it if possible.
* return        : Terminate procedure execution.
* **say "text"**    : Type a text or variable or expression value.
* sic Arg ON    : Change some SIC internal status.
* sort Key Vars : Sort variables according to another one.
* symbol        : Define, list and delete symbols.
* system        : Create or attach sub-processes, run system commands.
* type \[XX]     : List file XX or the stack.
* **@ XX \[P1 ...]** : Read commands from macro XX and executes them.

### LAS\ Command Language Summary ###
The first-priority part called in CLASS.

    help las\
* accumulate        : Add R and T observation.
* associate         : Add an Associated Array to the R observation
* **average**           : Average all the observations of the current index.
* **base \[arg]**       :  Subtract a baseline.
* *box*               : Draw a frame for data.
* catalog           : Load a line catalog
* consistency       : Check the consistency of the current index
* **copy**              : Write the current index into output file.
* drop num \[ver]    : Take a scan out of the current index.
* dump              : List some informations on the R spectrum.
* **extract X1 X2 \[U]** : Extract a subsection of the R spectrum.
* **file Type FileName**    : Define the input/output files.
* **find**              : Search the input file for observations.
* fits              : Write or read a fits file
* fold              : Fold a Frequency Switched spectrum.
* **get \[N]**           : Read a scan in the input file.
* **header**            : Display some header information on the R spectrum.
* ignore List       : Ignore scans from the Input file.
* **list \[in|out]**     : List header information about an ensemble of scans.
* load              : Build a 2D set of spectra from INDEX
* **modify**            : Edit and change the scan header.
* **multiply Fact**     : Multiply the R spectrum by fact.
* new_data          : Wait until new data present in input file.
* **plot**              : Plot the observation in R, with box and title.
* save \[name]       : Save the current parameters.
* **set**               : Enter a value for a parameter.
* **show Arg**          : Display some parameter.
* **spectrum**          : Plot the R observation or an associated array.
* **swap**              : Exchange the contents of the R and T buffers.
* tag Qual List     : Change the quality of scans in the Output file.
* title             : Write a header above the plotted frame.
* **update**            : Update R in the output file.
* **write \[Obs]**       : Write R in the output file.

### VECTOR\ Language Summary ###
    help vector\
* **fits**        : Convert between FITS files and Gildas images
* header      : List the header of a Gildas image
* **run TaskName**    : Activate a GILDAS task  
* spy \[Task]  : Look at current status of detached Tasks
* submit Task : Submit a GILDAS Task in batch queue GILDAS_BATCH
* **transpose**   : Transpose data cubes

### USER\ (Procedures)###
    help user\
* **input** = "@ p_input.greg"  
**input ProcName/?** : Show the help for this procedure/the list of availavle procedures.
* **go** = "@ p_go.greg"  
**go ProcName** : Execute a procedure.
* uvt_convert = "@ uvdat2uvfil.greg"

Pocedures for multichannel viewing:

 - **view**      : interactive viewing of spectra data cube
 - **3view**     : interactive viewing of position/velocity diagrams
 - **bit**       : plot a   color map of all or selected channels
 - map       : plot a contour map of all or selected channels
 - xv        : plot x-axis/velocity diagrams
 - vy        : plot velocity/y-axis diagrams
 - spectre   : plot spectra from a data cube
 - velocity  : plot mean, velocity and width maps
 - over      : Overlay bitmaps and contours of several images
 - *color, lut* : Fiddle Color Table
 
 Pocedures for analysis:
 
 - noise     : Compute noise histogram of data cubes
 - **moment**    : Compute mean, velocity and width maps

### ANALYSE\ Command Language Summary ###
    help analyse\
* comment           : Manipulate the COMMENT section of spectra
* divide            : Divide R spectrum by T spectrum
* **draw**              : Call the cursor or plot comments
* fill begin end    : Fill from begin to end with noise, blank, etc.
* fft               : Compute and edit Fourier Transform of R or P
* greg \[name]       : Make a TABLE or formatted file from current scan
* **lmv**               : Convert a data cube into a set of spectra
* **map** \[Match|Where]         : Plot a map of spectra (or only their location)
* memorize Arg      : Memorize the current observation
* **model Var**         : Generate a CLASS spectrum from a 1D variable
* noise \[S \[NEW]]   : Generate gaussian noise
* **print \[Arg]**       : Print values in a formatted file, or a table
* popup             : Zoom a spectrum from a STAMP, MAP or PLOT /INDEX
* reduce            : Reduce a SKYDIP
* resample Arg      : Resample a spectrum on a specified grid
* retrieve Arg      : Retrieve an observation from the memories
* smooth \[Arg...]   : Smooth the spectrum in R
* stamp             : Display all spectra in index on one plot
* strip File        : Create an image for Position-Velocity plots
* **table**             : Build a GILDAS table from the current index
* **xy_map**             : Build an LMV spectra cube from an XY table

### FIT\ Language Summary ###
    help fit\
* display            : Prints the results of the profile fit of R.
* **visualize \[N]**      : Plots the current fitted profile.
* **minimize**           : Performs a profile fit.
* **iterate**            : Iterates the profile fit.
* keep               : Saves Gaussian fit results in the output file.
* **lines \[N]**          : Enters the initial values for the profile fit.
* **method Arg**         : Selects the line profile for fits.
* residual \[N]       : Computes the residuals of the profile fit.
* result \[N]         : Computes the profile fit.

### GTVL\ Language Summary ###
    help gtvl\
* change      : Change some attributes of the plot.
* **clear Arg**   : Clear (some parts of) the plot or windows.
* compress    : Remove invisible parts of the plot.
* create Arg  : Create directory, windows or LUTs.
* destroy Arg : Destroys (some parts of) the plot or windows.
* device      : Open the graphic device.
* display     : List some parameters of the plot.
* gtv search  : Search for a GTV directory.
* **hardcopy**    : Get a printed copy of the plot.
* lens        : Call the lens on the active window.
* **lut \[Arg]**   : Change the color Look-Up-Table.
* metacode    : Save or load part of the plot to/from metacode file.
* refresh     : redraw all or some windows
* replicate   : Copy a directory to another place.
* zoom        : Zoom on the plot (possibly in another window).

### GREG1\ Language Summary ###
The first-priority part called in GreG.

    help greg1\
* axis      : Draws an axis according to its name
* **box**       : Makes a box labelled according to LIMITS and TICKSPACE
* column    : Reads the data file
* connect   : Connects (X,Y) pairs with line segments
* corners   : Display corners of the plotting surface.
* curve     : Connects (X,Y) pairs with a spline interpolation
* **draw**      : Calls the interactive cursor or execute detailed command
* errorbar  : Draws error bars on (X,Y) pairs
* histogram : Connects (X,Y) pairs as an histogram
* **label**     : Writes a string... according to options given
* **limits**    : Sets the limits of the plot (no args for auto)
* look      : Calls the cursor and executes a command when pressing key
* **pencil**    : Selects and defines the pen attributes
* points    : Draws markers at the (X,Y) pairs
* rule      : Makes a grid by joining axis tickmarks
* **set**       : Modifies some basic parameters
* **show**      : Shows basic parameters
* tickspace : Sets tick intervals for BOX or AXIS
* values    : Write the Y or Z values at the (X,Y) positions

### GREG2\ Language Summary ###
The first-priority part called in GreG.

    help greg2\
* convert     : Converts data in the X,Y buffer in the current projection.
* ellipse     : Draws an ellipse in User coordinate.
* **extrema**     : Shows minimum and maximum of the Regular Grid array.
* grid        : Plots a Grid in (A,D) with steps As and Ds (in degrees).
* **levels**      : Sets the contour levels.
* mask        : Masks part of a regular grid map.
* **mean**        : Computes statistics on map values.
* perspective : Makes a 3-D perspective of the Regular Grid array.
* **plot**        : Plots a SIC image variable to the window.
* **polygon**     : Defines a polygon for use by MASK and MEAN.
* projection  : Defines a spherical projection.
* random_map  : Creates a Regular Grid array from randomly sampled data.
* resample    : Resamples the Regular Grid array on a different Grid.
* rgdata      : Reads/creates a 2-D map and put it in the Regular Grid array.
* rgmap       : Draws contour lines for the Regular Grid array.
* strip       : Extracts a strip from the Regular Grid array.
* wedge       : Draws wedges.
* write       : Saves an internal buffer on a file.

### GREG3\ Language Summary ###
The first-priority part called in GreG.

    help greg3\
* **image \[Filename]** : Reads the GDF map Filename. Default extension is .GDF
* kill             : Kills pixels.
* spectrum         : Extracts or compute a mean spectrum from an image.

## Files
### File Format
Default extension of GILDAS Data Format is \*.gdf.
