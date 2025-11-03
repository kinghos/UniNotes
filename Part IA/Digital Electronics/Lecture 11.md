#### Potential dividers
$V_{x}=V\left( \frac{R_{2}}{R_{1}+R_{2}} \right)$
where V is the total voltage across both resistors.
![[PotentialDivider.png]]Plotting amps with voltage, you can plot the current/voltage curve for $R_2$. Then consider how $V_1$ is reflected in $V_2$, i.e. as $V_1$ increases $V_2$ decreases. Plotting both curves simultaneously gives the voltage at the point of intersection
For a non-linear device, you would plot its V-I characteristic in place of the linear characteristic.

### Transistors
Useful devices can be made by combining n and p type semiconductors to form a p-n junction. Electrons and holes diffuse across the junction due to the large concentration gradient. This leaves a space-charge region with no free charges. This gives rise to an electric field that opposes diffusion
Equilibrium is reached where no more charges move across the junction.

A device with a single p-n junction forces current to only flow through in one direction, i.e. a diode

##### n-Channel MOSFET
Current flow from D to S ($I_{DS}$) is controlled by the voltage applied between G and S ($V_{GS}$) i.e. G has to be +ve wrt S for current $I_{DS}$ to flow.
![[MOSFET.png]]
When there is a gate voltage applied, electrons are attracted to the underside of the gate, so this region is "inverted" and becomes n-type. This region is known as the channel. There is now a continuous path from S to D, so the transistor is on. 

##### p-Channel MOSFET
These are the opposite, where the charge carriers are holes. G has to be negative for the transistor to turn on.