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
1. The script generates a numerical table (table 1) for a range of [max(0,x-10), x+10]. In case of assignees is less than the number of groups, table 1 limits the number of groups to assignees (column a in Table 1).
2. Columns project time average rate of change and cost average rate of change can be viewed as empirical estimations of the discrete derivative of T(x) and C(x)
3. Table 2 contains values of function M(x) in the range [max(a,x), x+10]. The function forms one of the decision boundaries.
4. Table 3 indicates the minimum r1 required with given x and a for M(x) yield a non-negative margin.
5. r1/r2 (0.5~1): used as the coefficient of efficiency within/between the group. A low coefficient can indicate the task is hard to parallelize and/or the group's cohesion is low.


### note: 
1. The model only focuse on the overheads'(meetings, overlapping works, long discussion and miscommunication etc.) effects on project time and productivities. Benefits in group settings such as better quality work, new ideas and decrease in shared workload should not be ignored when making decisions on team size.
2. A [google sheet](https://docs.google.com/spreadsheets/d/1-kNHM5otdXNKMPb-EecDQZw4IOYc2mlzqqTKs5px_cg/edit?usp=sharing) with adjustable parameters for empirical samples and visualization
