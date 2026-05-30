# Splitting methods

The `integrators.txt` file contains an extensive collection of symplectic partitioned Runge–Kutta and Runge–Kutta–Nyström splitting coefficients for the numerical integration of Hamiltonian systems and second-order ordinary differential equations.

For a separable Hamiltonian

$$
H(q,p)=T(p)+V(q)
$$

a splitting scheme may be written as

$$
\Phi_h = e^{h c_1 L_V} e^{h d_1 L_T} e^{h c_2 L_V} e^{h d_2 L_T} \cdots e^{h c_s L_V} e^{h d_s L_T}
$$

The corresponding integration algorithm is

$$
\begin{aligned}
(q_0,p_0) &\gets (q,p) \\
\text{for } i=1,\dots,s: \\
p_i &\gets p_{i-1} - h c_i \nabla V(q_{i-1}) \\
q_i &\gets q_{i-1} + h d_i \nabla T(p_i)
\end{aligned}
$$

For separable Hamiltonian systems, the roles of (T) and (V) may often be exchanged in SPRK formulations by reversing the drift–kick ordering. The `integrators.txt` naming convention retains $c_1$ as the leading coefficient regardless of interpretation.

An equivalent ordering is therefore

$$
\begin{aligned}
(q_0,p_0) &\gets (q,p) \\
\text{for } i=1,\dots,s: \\
q_i &\gets q_{i-1} + h c_i \nabla T(p_{i-1}) \\
p_i &\gets p_{i-1} - h d_i \nabla V(q_i)
\end{aligned}
$$

Proper implementation may additionally require consideration of:

* the non-interchangeable role of drift and kick operators in RKN formulations
* methods with a “first same as last” (FSAL) structure when $d_s=0$
* explicit time dependence in nonautonomous systems
* compensated summation
* alternative formulations such as extended phase-space methods for nonseparable Hamiltonian systems or applications for constrained Hamiltonian systems

The file also includes a number of macros that must be interpreted, particularly for higher-order composition methods, coefficient manipulation and comment blocks. These macros are interpreted by [Zymplectic](https://github.com/Zymplectic/Zymplectic-Project) using up to 512-bit precision. The corresponding methods can also be found in the referenced literature.

:exclamation: The references listed below may not exactly match the representations used in `integrators.txt`:
- The naming conventions used for different methods may differ from those found in the literature. Many original authors have not assigned explicit names to their methods. Suggestions for renaming are welcome
- Coefficients are often expressed in cumulative form in the literature. They are consistently presented as $(c,d)$ in `integrators.txt`
- Coefficients published in the literature occasionally contain only a limited number of accurate digits. These methods have been revisited by Zymplectic, with coefficients extended to up to 77 correctly rounded digits
- Certain coefficients are presented algebraically in the literature but are represented numerically in `integrators.txt`

`integrators.txt` is published and maintained as part of the [Zymplectic project](https://github.com/Zymplectic/Zymplectic-Project)

## References

1. Hairer, E., Lubich, C., & Wanner, G. (2006). *Geometric Numerical Integration: Structure-Preserving Algorithms for Ordinary Differential Equations* (2nd ed.). Springer Series in Computational Mathematics, Vol. 31. Springer. [https://doi.org/10.1007/3-540-30666-8](https://doi.org/10.1007/3-540-30666-8)

2. Hairer, E., Lubich, C., & Wanner, G. (2006). *Geometric Numerical Integration: Structure-Preserving Algorithms for Ordinary Differential Equations* (2nd ed.). Springer Series in Computational Mathematics, Vol. 31. Springer. [https://doi.org/10.1007/978-3-662-05018-7](https://doi.org/10.1007/978-3-662-05018-7)

3. McLachlan, R. I. (1995). Composition methods in the presence of small parameters. BIT Numerical Mathematics, 35(2), 258–268. [https://doi.org/10.1007/BF01737165](https://doi.org/10.1007/BF01737165)

4. Iserles, A., Ramaswami, G., & Sofroniou, M. (1998). Runge–Kutta methods for quadratic ordinary differential equations. BIT Numerical Mathematics, 38, 315–346. [https://doi.org/10.1007/BF02512370](https://doi.org/10.1007/BF02512370)

5. Auzinger, W., Hofstätter, H., Ketcheson, D., & Koch, O. (2017). Practical splitting methods for the adaptive integration of nonlinear evolution equations. Part I: Construction of optimized schemes and pairs of schemes. BIT Numerical Mathematics, 57(1), 55–74. [https://doi.org/10.1007/s10543-016-0626-9](https://doi.org/10.1007/s10543-016-0626-9)

6. Farrés, A., Laskar, J., Blanes, S., Casas, F., Makazaga, J., & Murua, A. (2013). High precision symplectic integrators for the Solar System. *Celestial Mechanics and Dynamical Astronomy, 116*(2), 141–174. [https://doi.org/10.1007/S10569-013-9479-6](https://doi.org/10.1007/S10569-013-9479-6)

7. Forest, E., & Ruth, R. D. (1990). Fourth-order symplectic integration. *Physica D: Nonlinear Phenomena, 43*(1), 105–117. [https://doi.org/10.1016/0167-2789(90)90019-L](https://doi.org/10.1016/0167-2789%2890%2990019-L)

8. Yoshida, H. (1990). Construction of higher order symplectic integrators. *Physics Letters A, 150*(5–7), 262–268. [https://doi.org/10.1016/0375-9601(90)90092-3](https://doi.org/10.1016/0375-9601%2890%2990092-3)

9. Suzuki, M. (1990). Fractal decomposition of exponential operators with applications to many-body theories and Monte Carlo simulations. *Physics Letters A, 146*(6), 319–323. [https://doi.org/10.1016/0375-9601(90)90962-N](https://doi.org/10.1016/0375-9601(90)90962-N)

10. Okunbor, D. I., & Skeel, R. D. (1994). Canonical Runge–Kutta–Nyström methods of orders five and six. Journal of Computational and Applied Mathematics, 51(3), 375–382. [https://doi.org/10.1016/0377-0427(92)00119-T](https://doi.org/10.1016/0377-0427(92)00119-T)

11. Blanes, S., Casas, F., Escorihuela-Tomàs, A., & Ros, J. (2022). Efficient symplectic splitting methods for near-harmonic separable Hamiltonian systems. *Applied Numerical Mathematics, 182*, 210–230. [https://doi.org/10.1016/j.apnum.2022.07.010](https://doi.org/10.1016/j.apnum.2022.07.010)

12. Monovasilis, T., & Simos, T. E. (2007). Symplectic methods for the numerical integration of the Schrödinger equation. Computational Materials Science, 38(3), 526–532. [https://doi.org/10.1016/j.commatsci.2005.09.011](https://doi.org/10.1016/j.commatsci.2005.09.011)

13. Auzinger, W., Hofstätter, H., Ketcheson, D. I., & Koch, O. (2019). Practical splitting methods for the adaptive integration of nonlinear evolution equations. *Computer Physics Communications, 234*, 106–115. [https://doi.org/10.1016/j.cpc.2018.08.003](https://doi.org/10.1016/j.cpc.2018.08.003)

14. Schlier, Ch., & Seiter, A. (2000). High-order symplectic integration: an assessment. Computer Physics Communications, 130(1–2), 176–189. [https://doi.org/10.1016/S0010-4655(00)00011-4](https://doi.org/10.1016/S0010-4655(00)00011-4)

15. Omelyan, I. P., Mryglod, I. M., & Folk, R. (2003). Symplectic analytically integrable decomposition algorithms: Classification, derivation, and application to molecular dynamics, quantum and celestial mechanics simulations. Computer Physics Communications, 151(3), 272–314. [https://doi.org/10.1016/S0010-4655(02)00754-3](https://doi.org/10.1016/S0010-4655(02)00754-3)

16. Blanes, S., & Moan, P. C. (2002). Practical symplectic partitioned Runge–Kutta and Runge–Kutta–Nyström methods. Journal of Computational and Applied Mathematics, 142(2), 313–330. [https://doi.org/10.1016/S0377-0427(01)00492-7](https://doi.org/10.1016/S0377-0427(01)00492-7)

17. Sofroniou, M., & Spaletta, G. (2005). Derivation of symmetric composition constants for symmetric integrators. Optimization Methods and Software, 20(4–5), 597–613. [https://doi.org/10.1080/10556780500140664](https://doi.org/10.1080/10556780500140664)

18. Bandrauk, A. D., & Shen, H. (1994). High-order split-step exponential methods for solving coupled nonlinear Schrödinger equations. Journal of Physics A: Mathematical and General, 27(21), 7147–7155. [https://doi.org/10.1088/0305-4470/27/21/030](https://doi.org/10.1088/0305-4470/27/21/030)

19. McLachlan, R. I., & Atela, P. (1992). The accuracy of symplectic integrators. Nonlinearity, 5(2), 541–562. [https://doi.org/10.1088/0951-7715/5/2/011](https://doi.org/10.1088/0951-7715/5/2/011)

20. Kahan, W., & Li, R.-C. (1997). Composition constants for raising the orders of unconventional schemes for ordinary differential equations. *Mathematics of Computation, 66*(219), 1089–1099. [https://doi.org/10.1090/S0025-5718-97-00873-9](https://doi.org/10.1090/S0025-5718-97-00873-9)

21. Omelyan, I. P., Mryglod, I. M., & Folk, R. (2002). Optimized Verlet-like algorithms for molecular dynamics simulations. *Physical Review E, 65*(5), 056706. [https://doi.org/10.1103/PhysRevE.65.056706](https://doi.org/10.1103/PhysRevE.65.056706)

22. Ruth, R. D. (1983). A canonical integration technique. *IEEE Transactions on Nuclear Science, 30*(4), 2669–2671. [https://doi.org/10.1109/TNS.1983.4332919](https://doi.org/10.1109/TNS.1983.4332919)

23. Calvo, M. P., & Sanz-Serna, J. M. (1993). Variable steps for symplectic integrators. *SIAM Journal on Scientific and Statistical Computing, 14*(4), 936–952. [https://doi.org/10.1137/0914073](https://doi.org/10.1137/0914073)

24. McLachlan, R. I. (1995). On the numerical integration of ordinary differential equations by symmetric composition methods. *SIAM Journal on Scientific Computing, 16*(1), 151–168. [https://doi.org/10.1137/0916010](https://doi.org/10.1137/0916010)

25. Gürkan, M. A. (2012). Fifth Order Runge–Kutta–Nyström Methods with Complex Coefficients. arXiv preprint arXiv:1203.3279. [https://doi.org/10.48550/arXiv.1203.3279](https://doi.org/10.48550/arXiv.1203.3279)

26. Morales, M. E. S., Costa, P. C. S., Pantaleoni, G., Burgarth, D. K., Sanders, Y. R., & Berry, D. W. (2022). Selection and improvement of product formulae for best performance of quantum simulation. arXiv preprint arXiv:2210.15817. [https://doi.org/10.48550/arXiv.2210.15817](https://doi.org/10.48550/arXiv.2210.15817)

27. Tsitouras, Ch. (1999). A tenth order symplectic Runge–Kutta–Nyström method. *Celestial Mechanics and Dynamical Astronomy, 74*(3), 223–230. [https://doi.org/10.1023/A:1008346516048](https://doi.org/10.1023/A:1008346516048)

28. Laskar, J., & Robutel, P. (2001). High order symplectic integrators for perturbed Hamiltonian systems. *Celestial Mechanics and Dynamical Astronomy, 80*(1–2), 39–62. [https://doi.org/10.1023/A:1012098603882](https://doi.org/10.1023/A:1012098603882)

[1]: https://cir.nii.ac.jp/crid/1363107369548511232 "Geometric Numerical Integration | CiNii Research"
