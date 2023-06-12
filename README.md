### Parameters:
$x$: number of assignees\
$t$: estimated project workload for a single dev (hours)\
$r_1$: intra-group productivity coefficient\
$r_2$: inter-group productivity coefficient\
$a$: Number of groups assigned to the project\
$c$: average capability

### Functions:
$I(x)$: Individual productivity

$$I(x)=r_1^{(\frac{x}{a}-1)} \cdot r_2^{(a-1)} \cdot c$$


$G(x)$: Group productivity

$$G(x)=x \cdot I(x)=x \cdot r_1^{(\frac{x}{a}-1)} \cdot r_2^{(a-1)} \cdot c$$


$T(x)$: Function of the estimated project time with x  assignees (hours)

$$T(x)=\frac{t}{G(x)}=\frac{t}{x \cdot r_1^{(\frac{x}{a}-1)} \cdot r_2^{(a-1)} \cdot c}$$


$C(x)$: Function of the estimated project cost with $x$ assignees (in dev hours)

$$C(x)=\frac{t}{I(x)}=\frac{t}{r_1^{(\frac{x}{a}-1)} \cdot r_2^{(a-1)} \cdot c}$$


$M(x)$: marginal benefit of increase assignees

$$M(x)=-\frac{dT}{dx}-\frac{dC}{dx}=\frac{t \cdot (x \cdot ln(r1) \cdot (1+x)+a)}{a \cdot x^2 \cdot r_1^{(\frac{x}{a}-1)} \cdot r_2^{(a-1)} \cdot c}, x \geq a$$


$R(x)$: Threshold r1, minimum r1 required to have a non-negative margin with given number of groups and number of assignees

$$R(x)=e^{-\frac{a}{x \cdot (1+x)}}$$


## How to use:


### note: 
1. The model only focuse on the overheads'(meetings, overlapping works, long discussion and miscommunication etc.) effects on project time and productivities. Benefits in group settings such as better quality work, new ideas and decrease in shared workload should not be ignored when making decisions on team size.
2. A [google sheet](https://docs.google.com/spreadsheets/d/1-kNHM5otdXNKMPb-EecDQZw4IOYc2mlzqqTKs5px_cg/edit?usp=sharing) with adjustable parameters for empirical samples and visualization
