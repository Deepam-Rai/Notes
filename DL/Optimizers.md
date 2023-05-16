
## Gradient descent
1. $\gamma \gets$ learning rate, a scalar
2. t $\gets$ 0, iteration number
3. $\theta = [w,b] \gets$ Random initialization
4. max_iterations $\gets$ a positive integer
5. while (t < max_iterations) do
	1. $w_{t+1} \gets w_t - \gamma \nabla w_t$
	2. $b_{t+1} \gets b_t - \gamma \nabla b_t$
	3. $t \gets t+1$

----
## Momentum based optimization

$$\large m_t = \gamma m_{t-1} + \neta \nabla_\theta L(\theta)$$

$$\large \theta_{t+1} = \theta_t - m_t$$

----
# Adaptive Learning Rate Algorithms

## AdaGrad
- Accumulates historical gradients.

$K =$ number of parameters,  
$t =$ current iteration,  
$\theta_t =$ vector of dim $K$ containing learning rate for all parameters,   
$r_t =$ gradient accumultation vector of dim $K$ at iteration $t$,  
$g_t =$ vector of dim $K$ containing gradients of parameters at iteration $t$,  
$\epsilon =$ global learning rate, a scalar,  
$\delta \approx0$, a tiny number to avoid divide by zero,  
$\circ =$ element wise multiplication,  

Gradient accumulation vector is initially set to 0:
$\large r_0 =0$

At every iteration:
$$\large\begin{aligned}
r_t &= r_{t-1} + g_t\circ g_t \\ \\
\theta_t &= \theta_{t-1} - \left[\frac{\epsilon}{\delta + \sqrt{r_t}}\right]\circ g_t
\end{aligned}$$

where addition and division operators are broadcasted as needed and applied element wise.  
- Dimension of all these vectors = number of parameters.
- Parameters with large gradients experience rapid decrease in learning rate.
- It may get stuck at saddle points.


## RMSProp
- Give lower weightage to remotely past gradients.
- Calculates exponentially weighted moving average of gradients

$K =$ number of parameters,  
$t =$ current time step,  
$\theta_t =$ vector of dim $K$ containing learning rate for all parameters,   
$t =$ current iteration,  
$\rho =$ decay factor,  
$r_t =$ gradient accumulation vector at iteration $t$,  
$\epsilon =$ global learning rate, a scalar,  
$\delta \approx0$, a tiny number to avoid divide by zero,  
$\circ =$ element wise multiplication,  

$$\large r_t = \rho r_{t-1} + (1-\rho)g_t\circ g_t$$

$$\large \theta_t = \theta_{t-1} - \left[ \frac{\epsilon}{\delta + \sqrt{r_t}}\right]\circ g_t$$

where addition and division operations are broadcasted as required.  

- $\rho$ in a way controls the window of past gradients to consider.


## Adam
- Approximates first and second moment of gradients. To make the approximation unbiased to initializtaion, the formula becomes as it is.

$\beta_1=$ weightage given to historical first moment,  
$\beta_2=$ weightage given to historical second moment,  
$m_t =$ approximation of first moment,   
$v_t =$ approximation of second moment,  
$\tilde m_t =$ unbiased estimation of first moment,  
$\tilde v_t =$ unbiased estimation of second moment,  

$$\large \begin{aligned}
m_t &= \beta_1m_{t-1} + (1-\beta_1)g_t\\
v_t &= \beta_2 v_{t-1} + (1-\beta_2)g_t \circ g_t \\ \\
\tilde m_t &= \frac{m_t}{1-\beta_1^t} \\
\tilde v_t &= \frac{ v_t}{1-\beta_2^t} \\ \\
\theta_t &= \theta_{t-1} - \left[\frac{\epsilon}{\delta + \sqrt(v_t)}\right]\circ m_t
\end{aligned}$$

----
