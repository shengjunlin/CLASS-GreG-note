# CLASS/GreG-note
CLASS: Continuum and Line Analysis Single-dish Softwares

GreG: Grenoble Graphic

## Content ##
1. [Document](#doc)
2. [Variable](#variable)
3. [Flow Control](#flow)
4. [Data Format](#data)
5. [Spectrum Plot](#plot) 
6. [Fitting](#fitting)
7. [Map](#grid_map)
8. [Other](#other)
9. [References](#ref)

## <a name="doc"></a>1. Document ##
<code>help</code> Show the list of availavle languages and commands.  
<code>help LangName\\</code> Show the list of availavle commands.  
<code>help [LangName\\]CommandName [Subtopic name]</code> Show the help for this command [in the subtopic].  
To execute the command, <code>[LangName]CommandName</code>.  

<code>help task [Group name]</code> Show the help summary of all available tasks [in the group].  
<code>help run TaskName</code> Show the help for this task.  
To execute the task, <code>run TaskName</code>.  

<code>help input</code> Show the help for <code>input</code> and <code>go</code>.  
<code>input ?</code> Show the list of availavle procedures.  
<code>input ProcName</code> Show the help for this procedure.  
To execute the procedure, <code>go ProcName</code>.  

<code>help function</code> Show the list of availavle functions.  
<code>help function FuncName</code> Show the help for this functions.  

### Spectical Operator ###
<code>$ SHELL_Command [-Opts] [Args]</code> Interacting with the shell.  
<code> ! </code> Start a comment.  
<code> ; </code> Delimiter operator (command separator).  
<code>Ctrl + u</code> Remove the current input characters.  

### Command History ###
Search commands backwards : Hit up-arrow key.  
Partially search commands : Type the beginning of a previous command, and then hit up-arrow

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

### VECTOR\ Language Summary ###
    help vector\
* **fits**        : Convert between FITS files and Gildas images
* header      : List the header of a Gildas image
* **run TaskName**    : Activate a GILDAS task  
* spy \[Task]  : Look at current status of detached Tasks
* submit Task : Submit a GILDAS Task in batch queue GILDAS_BATCH
* **transpose**   : Transpose data cubes

### USER\ (Procedures) ###
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

### MAP\ ###
        help map\
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

## 2. <a name="variable"></a>Variable ##

Types are <code>REAL</code>, <code>INTEGER</code>, <code>DOUBLE</code>, <code>LOGICAL</code>, and <code>CHARACTER</code>.

Define a integer variable and assign a value

        define integer output_data
        let [=] output_data 0

## 3. <a name="flow"></a>Flow Control ##

* Mathematical operator: <code>+</code>, <code>-</code>, <code>\*</code>, <code>/</code>, <code>|</code>(division too), etc.
* Logical operator: <code>.eq.</code>, <code>.gt.</code>, <code>.le.</code>, etc.

        if output_data.eq.1
            [...]

* IF block

        if [cond 1]
            [case 1]
        else if [cond 2]
            [case 2]
        else
            [case 3]
        endif

* FOR block

        for i n1 n2 n3 to n4 by n5 n6 to n7
            [...]
        next
The index, i,  will go through n1, n2, n3, n3+*n5*, n3+*2\*n5*, ..., n4,  
n6, n6+*1*, n6+*2*, ..., n7. n_j's can be non-integers.

## 4. <a name="data"></a>Data Format ##
### GILDAS Format ###
Mainly work with VECTOR, USER commands.
A cube data.
Default extension is \*.gdf.  

Two types:
* Table : 2-dimension array + header about its dimensions.  
Make a CLASS format data, <code>DataName.30m</code>, become a Table (must be <code>DataName.tab</code>).  

        ANALYSE\table DataName.tab [new] [/range Xmin Xmax Unit] [/nocheck [source|position|line]]
* Image : 4-dimension array + header about WCS, tele, etc.  
Make a Table, <code>TableName.tab</code>, become an Image (must be <code>TableName.lmv</code>).

        MAP\xy_map TableName.tab [/nogrid] [/type lmv]
LMV spectra cubes are Images. L: RA(1), M: Dec(2), V: Velocity(3).  
Change the sequence of axes of LMV cubes.  

        VECTOR\transpose InputFileName OutputFileName OutputOrder
The outputs of task <code>go moment</code>, \*.mean (0th mom), \*.velo (1st mom). \*width (2nd mom), belong to 2d Images.  
Convert between FITS files and Gildas images or tables.  

        VECTOR\fits OutputFile.fits from InputFile.gdf
        VECTOR\fits InputFile.gdf to OutputFile.fits

### CLASS Format ###
Mainly work with LAS, ANALYSE, FIT commands.
A set of spectra.
Default extension is \*.30m.

R and T Memories:  
CLASS keeps 2 observations in memory, in two different buffers, called <code>R</code> and <code>T</code>. The <code>R</code> memory is the only one that may be accessed directly; the <code>T</code> memory is only used for operations on spectra.  
<code>LAS\swap</code> exchanges both memories.

<code>LAS\file in DataName.30m</code> Open an existing CLASS data  

<code>LAS\file out DataName.30m</code> Open an existing CLASS data as output (to be written/updated)  

<code>LAS\file out DataName.30m single|multiple [/overwrite]</code>  
Open a new CLASS data as output.  
The single mode only allow to have one spectrum for an ObservationNumber, and vice versa.

<code>LAS\file update DataName.30m</code> Open an existing file to update. <code>write</code> is not allowed.

<code>LAS\file both DataName.30m</code> Open an existing MULTIPLE file to read and write.

<code>LAS\find [/line name] [/offset o1 o2] [/source name] ... </code> Search from the input data and build an Index

<code>LAS\show file</code> Show the file type.

<code>LAS\list [in|out]</code> List the input Index or output Index.

<code>LAS\get [N [ver]|first|last|next]</code> Copy <code>R</code> into <code>T</code>, and load the ObservationNumber N in <code>R</code>.

### Examples ###
Open a data. Display the header of a spectrum.

        file in DataName.30m
        find; list
        get first ! "get" puts an Obs into the R buffer.
        header
        
Upate (Overwrite) the LAST version of the observation in the R buffer in the output data.

        file update DataName.30m
        find /line N2H+* /offset * 0 ! "*" represents any characters
        for i 1 to found
            get next
            modify source L0000 ! Modify the R buffer
            modify linename N2D+(1-0)
            modify position 00:00:00.00 00:00:00.0 ! RA & Dec
            modify velocity 7.5 ! in km/s
            update ! Overwrite/update the R buffer to the last Obs
        next
        
Writes the observation in the R buffer onto the output file. A new ObservationNumber is created.

        file both DataName.30m ! A MULTIPLE data
        find /line N2H+* /offset * 0
        for i 1 to found
            get next
            modify [...]
            write ! Write the R buffer into a new Obs
        next

Write a new output data with the modification.
        
        file out DataName_new.30m single
        file in DataName.30m
        find
        for i 1 to found
            get next
            modify [..]
            write
        next
        
Copy a data.

        file out DataName_new.30m single
        file in DataName.30m
        find; copy

Write spectra from a CLASS data to ASCII files.

        file in DataName.30m
        for d -12 to 24 by 12
            for a 0 to 36 by 12
                find /off a d
                if found.gt.0
                    get next
                    set unit v f
                    sic output Dir/n2hp10_'a'_'d'.dat ! Open the file.
                    for i 1 to channels
                        ! Redirect SIC\say into the file.
                        say 'rx[i]' 'ry[i]' ! rx & ry mean the x/y axis of the R buffer
                    next
                    sic output ! Without arg, close the file.
                endif
            next
        next
                    

## 5. <a name="plot"></a>Spectrum Plot ##

<code>LAS\plot</code> is equivalent to

        clear
        box
        spectrum
        title

### Examples ###
Average all found spectra; then plot.

        file in DataName.30m
        find; list
        average /nocheck position ! "average" puts an Obs into the R buffer.
        plot

Draw a vertical line and add a label on the plot and save it as a image file.

        plot
        GREG\pen /colour 1 ! red
        GREG\draw r 7.82 0 /user  ! r for relocate, a staring point
        GREG\draw l 7.82 1 /user  ! l for line, the end point for a line
        GREG\draw text 7.71 0.3 "v\d0(DCO\u+ 1-0)=7.82" 5 90 /user
        GREG\pen /colour 0 ! black
        hardcopy dcop_10_vlsr_off_+00_+00.png /device png /overwrite


## 6. <a name="fitting"></a>Fitting ##

Before fitting, one should establish a baseline by <code>LAS\base</code>.

        file in provisional/prov_n2hp_10.30m
        file out n2hp_10.30m single
        set unit v f
        set mode x -5 20
        set window 6.9 8.6
        for d -60 to 60 by 10  ! Dec
            for a -60 to 60 by 10  ! RA
                find /off a d
                if found.gt.0
                    get next
                    plot
                    draw window
                    base 8 /plot  ! Fit with an 8th-order polynomial. Then put
                                  ! the extracted spectrum into the R buffer and store
                                  ! the previous spectrum in the T buffer.
                                  ! /plot will display the new spectra in the R buffer.
                    pause  ! Type 'c' to continue, or 'quit' to cancel all loop
                    write  ! Write the baseline-extracted spectra into file
                endif
            next
        next

Use <code>LAS\swap</code> to undo the baseline extraction.

        plot; draw window
        base 5 /plot
        swap  ! Exchange buffer T and R. The old spectra is recovered in the R buffer.
        plot  ! Plot again. You will find the display is the old spectra.
        base 4 /plot ! Try another order.

<code>FIT\method</code> can select a line profile for fitting.

        FIT\method gauss  ! Use a gaussian profile
        FIT\method hfs [filename]  ! Use a file for hfs fitting

The filename storing hfs profile should be (the example is N2H+ 1-0)

        7             ! 1st line: Number of components
        -8.0064 0.111 ! 1st column: Velocity shift, for each component,
        -0.6109 0.111 ! (in km/s) with respect to the reference
        0       0.259 ! component.
        0.956   0.185 ! 2nd column: The relative strength of each component.
        5.5452  0.111 ! Here, they are normalized.
        5.9842  0.185
        6.936   0.037

<code>FIT\minimize</code> will perform the fitting.

Once <code>minimize</code> has been executed, one can execute <code>FIT\iterate</code>
to perform the fitting again but by starting from the previous result.

<code>FIT\visualize</code> will display the fitted spectra profile.

        file in n2hp_10.30m
        find /offset 0 0; list; get first
        set unit v f; set mode x -5 20; set mode y -0.3 1.3
        set window 6. 9.
        plot; base 0 /plot
        method hfs n2hp_10.hfs
        minimize
        plot
        visualize /pen 3  ! 3 is green

## 7. <a name="grid_map"></a>Map ##

### Spectra Grid

        ANALYSE\map where ! Only displays the spectra locations with crosses
        ANALYSE\map match /grid ! Display spectra grid
        ANALYSE\map match /cell Size_X [Size_Y] ! Customize the cell size

#### Example
        file in dcop_10.gbt
        find
        set unit v f
        ! To selct the range to output
        set mode x 6 10
        set mode y -0.2 1.3
        clear
        map match /grid /base 1  ! 1 means red
        pause "type GREG\draw and type t to annotate"
        ! draw  ! Type "t" to annotate text
        ! >Text : DCO\u+ (1-0), x:6~10km s\u-\u1, y=-0.2-1.3K
        ! Type "e" to leave when the cursor is on the greg window

        pause "type GREG\draw and type b on the plot to find the dimension of a box, x1 x2 y1 y2"
        GREG\set box 20.71 21.76 7.329 8.379  ! x1 x2 y1 y2
        pen /colour 0
        set expand 0.5 ! font size
        set unit v v
        box

        hardcopy dcop_10_spec /device eps /overwrite  ! EPS file
        $ epstopdf dcop_10_spec.eps  ! PDF file
        $ convert -flatten -density 300 dcop_10_spec.pdf dcop_10_spec.png  ! PNG file

### Moment Maps

        go moment

A window will display to edit parameters and generate a file <code>moments.init</code>
storing the parameters. If <code>moments.init</code> previously exists, the window will load the parameters.
This task will produce three files, \*.mean (0th mom), \*.velo (1st mom), and \*.width (2nd mom), in the GILDAS formats.
Then use <code>VECTOR\fits</code> to convert the GILDAS formats to FITS formats.

Another way is to use ANALYSE commands.

        ANALYSE\print area LIST [/output File]
        ANALYSE\print moment LIST [/output File]

For example, <code>LIST</code> can be -2 15, namely integrated from -2 to 15 km/s which has
the same format as the FOR-NEXT loop. Each row in the output has (1) the observation number,
(2,3) the offsets in current angle units. (4) is the areas for the <code>area</code> case and
(4,5,6) are area, position, width for the <code>moment</code> case. The output file is in the
ASCII format.

To obtain FITS files, we need to convert the ACSII files to GILDAS first; then convert them to FITS files.

        GREG1\column x 2 y 3 z 4 /file File ! read ra_offset, dec_offset, mom0 from a area file
        
        ! Convert x_offset to be RA_offset
        define real x_ra /like x
        let x_ra = -x
        
        GREG2\rgdata x_ra y z /blanking 0 ! create a regular grid
        ! Another way is to interpolate to a finer meash or create from a irregular sampling
        ! GREG2\random_map 100 100 /var x_ra y z /blanking 0

        GREG1\set system equatorial 1950 ! coordinates
        ! Define a projection: RA0, Dec0, rotation, proj. type
        ! Some type options: gnomonic  (makes CTYPE1|2='-----TAN')
        !                    azimuthal (makes CTYPE1|2='-----ARC')
        !                    radio     (makes CTYPE1|2='-----GLS')
        GREG2\projection 4:07:50 25:02:13 0.0 /type gnomonic
        ! Set the offset unit used by the input File
        GREG1\set angle_unit second

        ! Save as an image (*gdf)
        GREG2\write image mom0.gdf
        ! Save a fits file
        VECTOR\fits mom0.fits from mom0.gdf

Afterwards, we need to correct the header values for CTYPE1|2 to be 'RA---XXX' and 'DEC--XXX' if they were '-----XXX'.

## 8. <a name="other"></a>Other ##

<code>sic edit vim</code> to change the default editor from a display window to vim.
It is useful when the task will show a large window for setting parameter; e.g, <code>run reproject</code>.
In contrast, <code>run reproject /edit</code> will turn into vim to finish the settings.


## <a name="ref"></a>References ##
<a href='https://www.iram.fr/IRAMFR/GILDAS/gildasli3.html#x6-3000' target="_blank">GILDAS Documentation</a>
