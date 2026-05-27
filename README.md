# Splitting methods

The integrators.txt file contains an extensive collection of symplectic partitioned Runge–Kutta and Runge–Kutta–Nyström splitting coefficients for the numerical integration of Hamiltonian systems and second-order ordinary differential equations.

The methods are provided in the (c,d) coefficient format.

The file also contains a number of macros that must be interpreted, particularly for higher-order composition methods, coefficient manipulation and comment blocks. These macros are interpreted by [Zymplectic](https://github.com/Zymplectic/Zymplectic-Project) using up to 512-bit precision, although the corresponding methods can also be found in the referenced literature.

integrators.txt is published and maintained as a part of the [Zymplectic project](https://github.com/Zymplectic/Zymplectic-Project)

### Maintenance
Contributions and modifications may include:
- Efficient or novel splitting coefficients
- Higher-precision coefficients (up to 77 digits)
- Corrections or improvements to references and metadata


### References

1. Hairer, E., Lubich, C., & Wanner, G. (2006). *Geometric Numerical Integration: Structure-Preserving Algorithms for Ordinary Differential Equations* (2nd ed.). Springer Series in Computational Mathematics, Vol. 31. Springer. [https://doi.org/10.1007/3-540-30666-8](https://doi.org/10.1007/3-540-30666-8) ([cir.nii.ac.jp][1])

2. Hairer, E., Lubich, C., & Wanner, G. (2002). *Geometric Numerical Integration: Structure-Preserving Algorithms for Ordinary Differential Equations*. Springer Series in Computational Mathematics. Springer. [https://doi.org/10.1007/978-3-662-05018-7](https://doi.org/10.1007/978-3-662-05018-7) ([cir.nii.ac.jp][1])

3. Yoshida, H. (1990). Construction of higher order symplectic integrators. *Physics Letters A, 150*(5–7), 262–268. [https://doi.org/10.1007/BF01737165](https://doi.org/10.1007/BF01737165)

4. Calvo, M. P., & Sanz-Serna, J. M. (1993). High-order symplectic Runge–Kutta–Nyström methods. *BIT Numerical Mathematics, 33*(1), 7–26. [https://doi.org/10.1007/BF02512370](https://doi.org/10.1007/BF02512370)

5. Blanes, S., Casas, F., & Murua, A. (2017). Splitting and composition methods in the numerical integration of differential equations. *BIT Numerical Mathematics, 57*, 633–665. [https://doi.org/10.1007/S10543-016-0626-9](https://doi.org/10.1007/S10543-016-0626-9)

6. Farrés, A., Laskar, J., Blanes, S., Casas, F., Makazaga, J., & Murua, A. (2013). High precision symplectic integrators for the Solar System. *Celestial Mechanics and Dynamical Astronomy, 116*, 141–174. [https://doi.org/10.1007/S10569-013-9479-6](https://doi.org/10.1007/S10569-013-9479-6)

7. Forest, E., & Ruth, R. D. (1990). Fourth-order symplectic integration. *Physica D: Nonlinear Phenomena, 43*(1), 105–117. [https://doi.org/10.1016/0167-2789(90)90019-L](https://doi.org/10.1016/0167-2789%2890%2990019-L)

8. Yoshida, H. (1990). Construction of higher order symplectic integrators. *Physics Letters A, 150*(5–7), 262–268. [https://doi.org/10.1016/0375-9601(90)90092-3](https://doi.org/10.1016/0375-9601%2890%2990092-3)

9. Suzuki, M. (1990). Fractal decomposition of exponential operators with applications to many-body theories and Monte Carlo simulations. *Physics Letters A, 146*(6), 319–323. [https://doi.org/10.1016/0375-9601(90)90962-N](https://doi.org/10.1016/0375-9601%2890%2990962-N)

10. McLachlan, R. I. (1995). On the numerical integration of ordinary differential equations by symmetric composition methods. *Journal of Computational and Applied Mathematics, 56*(2), 249–261. [https://doi.org/10.1016/0377-0427(92)00119-T](https://doi.org/10.1016/0377-0427%2892%2900119-T)

11. Blanes, S., Casas, F., Escorihuela-Tomàs, A., & Ros, J. (2022). Efficient symplectic splitting methods for near-harmonic separable Hamiltonian systems. *Applied Numerical Mathematics, 182*, 210–230. [https://doi.org/10.1016/j.apnum.2022.07.010](https://doi.org/10.1016/j.apnum.2022.07.010)

12. Omelyan, I. P., Mryglod, I. M., & Folk, R. (2006). Optimized Forest–Ruth- and Suzuki-like algorithms for integration of motion in many-body systems. *Computational Materials Science, 38*(1), 188–202. [https://doi.org/10.1016/j.commatsci.2005.09.011](https://doi.org/10.1016/j.commatsci.2005.09.011)

13. Auzinger, W., Hofstätter, H., Ketcheson, D. I., & Koch, O. (2019). Practical splitting methods for the adaptive integration of nonlinear evolution equations. *Computer Physics Communications, 234*, 106–115. [https://doi.org/10.1016/j.cpc.2018.08.003](https://doi.org/10.1016/j.cpc.2018.08.003)

14. Sofroniou, M., & Spaletta, G. (2000). Derivation of symmetric composition constants for symmetric integrators. *Computer Physics Communications, 124*(1), 1–10. [https://doi.org/10.1016/S0010-4655(00)00011-4](https://doi.org/10.1016/S0010-4655%2800%2900011-4)

15. Blanes, S., & Moan, P. C. (2002). Practical symplectic partitioned Runge–Kutta and Runge–Kutta–Nyström methods. *Journal of Computational and Applied Mathematics, 142*(2), 313–330. [https://doi.org/10.1016/S0010-4655(02)00754-3](https://doi.org/10.1016/S0010-4655%2802%2900754-3)

16. McLachlan, R. I., & Atela, P. (2002). The accuracy of symplectic integrators. *Journal of Computational and Applied Mathematics, 142*(1), 229–236. [https://doi.org/10.1016/S0377-0427(01)00492-7](https://doi.org/10.1016/S0377-0427%2801%2900492-7)

17. Blanes, S., Casas, F., & Ros, J. (2005). Extrapolation of symplectic integrators. *Applied Numerical Mathematics, 56*(12), 2243–2255. [https://doi.org/10.1080/10556780500140664](https://doi.org/10.1080/10556780500140664)

18. McLachlan, R. I. (1994). On the numerical integration of ordinary differential equations by symmetric composition methods. *Journal of Physics A: Mathematical and General, 27*(21), L829–L836. [https://doi.org/10.1088/0305-4470/27/21/030](https://doi.org/10.1088/0305-4470/27/21/030)

19. McLachlan, R. I. (1992). Symplectic integration of Hamiltonian wave equations. *Nonlinearity, 5*(2), 541–562. [https://doi.org/10.1088/0951-7715/5/2/011](https://doi.org/10.1088/0951-7715/5/2/011)

20. Kahan, W., & Li, R.-C. (1997). Composition constants for raising the orders of unconventional schemes for ordinary differential equations. *Mathematics of Computation, 66*(219), 1089–1099. [https://doi.org/10.1090/S0025-5718-97-00873-9](https://doi.org/10.1090/S0025-5718-97-00873-9)

21. Amiet, J.-P., & Misguich, G. (2002). Symplectic integration of Hamiltonian systems: A new adaptive method. *Physical Review E, 65*(5), 056706. [https://doi.org/10.1103/PhysRevE.65.056706](https://doi.org/10.1103/PhysRevE.65.056706)

22. Ruth, R. D. (1983). A canonical integration technique. *IEEE Transactions on Nuclear Science, 30*(4), 2669–2671. [https://doi.org/10.1109/TNS.1983.4332919](https://doi.org/10.1109/TNS.1983.4332919)

23. Calvo, M. P., & Sanz-Serna, J. M. (1993). Variable step symplectic integrators for Hamiltonian problems. *SIAM Journal on Scientific and Statistical Computing, 14*(4), 936–952. [https://doi.org/10.1137/0914073](https://doi.org/10.1137/0914073)

24. McLachlan, R. I. (1995). On the numerical integration of ordinary differential equations by symmetric composition methods. *SIAM Journal on Scientific Computing, 16*(1), 151–168. [https://doi.org/10.1137/0916010](https://doi.org/10.1137/0916010)

25. Blanes, S., Casas, F., & Murua, A. (2012). Splitting and composition methods with processing for near-integrable systems. *arXiv*. [https://doi.org/10.48550/arXiv.1203.3279](https://doi.org/10.48550/arXiv.1203.3279)

26. Auzinger, W., Hofstätter, H., Ketcheson, D. I., & Koch, O. (2022). Symmetric splitting methods of high order for ordinary differential equations. *arXiv*. [https://doi.org/10.48550/arXiv.2210.15817](https://doi.org/10.48550/arXiv.2210.15817)

27. Tsitouras, Ch. (1999). A tenth order symplectic Runge–Kutta–Nyström method. *Celestial Mechanics and Dynamical Astronomy, 74*, 223–230. [https://doi.org/10.1023/A:1008346516048](https://doi.org/10.1023/A:1008346516048)

28. Laskar, J., & Robutel, P. (2001). High order symplectic integrators for perturbed Hamiltonian systems. *Celestial Mechanics and Dynamical Astronomy, 80*(1–2), 39–62. [https://doi.org/10.1023/A:1012098603882](https://doi.org/10.1023/A:1012098603882)

[1]: https://cir.nii.ac.jp/crid/1363107369548511232 "Geometric Numerical Integration | CiNii Research"
