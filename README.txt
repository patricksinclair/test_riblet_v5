This is based on the gradient slippy riblet case.  We'll change it by changing the geometry to 4 riblets, all on the micron scale

This is the scaled down version based on the AkzoNobel riblet paper dimensions.

Boundary conditions changed to the ones from the pipe pdf, the ones used in the slippy riblet one.

Uniform U at the LHS, then hopefully poiseuille flow develops before it reaches the riblets.
///////////////////////////////////
Increased inlet velocity to 5 ms^-1, and also increased inlet channel length.
/////////////////////////////////////////////////////////////////////////////
Surface tension is far too high, changed it to 0.034.  This might still be too high, seeing as the surrounding fluid is water.  But see how things go for now
//////////////////////////////////////////////////////////////////////////////
Modified blockmeshdict so that it now has finer grading towards the riblet apexes.
Made the mesh overall coarser to try and speed things up.

Changed the inlet velocity based on the AkzoNobel riblet paper, and under the assumption that the flow profile has a linear gradient irl
Based on v = ([simulation h]/[experimental h])*[experimental v].  This gives us a v = 0.18 ms^-1.

We'll just use some ballpark numbers for the transport properties for now.  set both densities equal to water (1e3), make biofilm 1000 times more viscous.

Let's also try a few different surface tensions to see if that makes much of a difference.
///////////////////////////////////////////////////////
Going to run it for longer and also reduce the surface tension by factor of 10.
//////////////////////////////////////////////////////////////////////////
surface tension is currently at 1e-4.
Added mesh grading to the y-direction so it's more concentrated at the riblet peaks.  This way we can hopefully use a coarser overall mesh.
Increased courant number to 0.95.
Changed nBufferlayersR to from 2 -> 1 in constant/dynamicMeshDict.
/////////////////////////////////////////////////////////////////
There was some numerical noise, so I've added an x-gradient to the inlet/outlet x-cells refining.
