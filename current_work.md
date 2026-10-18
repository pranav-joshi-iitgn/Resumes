# Co-evolutionary GA optimisation for sparse array TFM with non-linear activation

Total focusing method is a computationaly heavy method for creating high quality images from ultrasound data. 
To reduce the computational burden while still getting high quality images, sparse array TFM is often used. In this method, only a subset of the total transducer elements are used for TFM. 
The subset to choose is typically optimised by maximizing metrics such as PSL and ISLR for a particular imaging grid using Genetic Algorithm (GA) or other optimisation strategies. 
Often, non-linear functions are applied to partial images before being summed and after the summation, e.g. $p^\text{th}$ root and $p^\text{th}$ power are applied to first amplify the small signal values for some signals to allow constructive interference to be amplified and then to suppress noise after final sum respectively. 
While this works well on software systems and on software-FPGA co-designed systems, applying this directly on the FPGA is hard since computational paths for $p^\text{th}$ root are long and would require a lot of resources. 

Instead of relying on specific functions such as $p^\text{th}$ root, this work aims to use learnt activation functions for the partial images that can be implemented on FPGA with little resource utilization; mainly through symbolic and linear regression with some FPGA-implementable basis functions.

This work also aims at developing a time-complexity optimised Cooperative Coevolutionary Genetic Algorithm (CCGA) strategy for evolving the activation functions and sparse array layouts.