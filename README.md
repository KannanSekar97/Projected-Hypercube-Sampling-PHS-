# Projected-Hypercube-Sampling-PHS

To address the existing limitations of reference vector generation method which is center biased and geometry dependent, we proposed a Projected Hypercube Sampling (PHS) that arbitrarily samples in the uniform hypercube to densely cover the space and on their edges, project them onto the reference hyperplane, from this required number of reference vectors are selected using greedy equidistant approach,and finally these reference vectors are constructed normal to the reference hyperplane (0-1 direction) to intersect the Pareto surface. The proposed framework explained below

<table align="center">
  <tr>
    <td align="center">
      <img width="320" height="340" alt="sampling_in_cube" src="https://github.com/user-attachments/assets/8f6f21c0-a365-4dc3-90de-224923e287ac" />
      <br/>
      <em>(a) Sampling in cube</em>
    </td>
    <td align="center">
      <img width="320" height="340" alt="projection_on_reference_hyperlane" src="https://github.com/user-attachments/assets/5c906f95-73f4-4261-ac97-092f1ab3c450" />
      <br/>
      <em>(b) Projection onto reference hyperplane</em>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img width="320" height="340" alt="1quidistance_reference_point_selection" src="https://github.com/user-attachments/assets/ef7948bc-ad85-41e0-ba21-2571a38b8888" />
      <br/>
      <em>(c) Equidistant reference point selection</em>
    </td>
    <td align="center">
      <img width="320" height="340" alt="parallel_reference_vector_construction" src="https://github.com/user-attachments/assets/e28a6173-e7d0-48db-a64f-d6db458560d0" />
      <br/>
      <em>(d) Parallel reference vector construction</em>
    </td>
  </tr>
</table>

<p align="center">
  <em>
  Overview of the proposed Projected Hypercube Sampling based reference vector generation.
  </em>
</p>

In this approach, the number of initial samples on the hypercube and the number of points per edge are use defined.

The Alpha parameterized covex Pareto front shapes shown below, we can see that the curvature of the pareto front increases as alpha increaes.
<table align="center">
  <tr>
    <td align="center">
      <img width="300" height="320" alt="Convex_alpha_1" src="https://github.com/user-attachments/assets/719d0971-0994-4a5b-b744-c3153a208d32" />
      <em>Convex PF $\alpha=1$</em>
    </td>
    <td align="center">
     <img width="300" height="320" alt="Convex_alpha_5" src="https://github.com/user-attachments/assets/f0efae3b-fe4a-41be-9f05-3adc681aa598" />
      <em>Convex PF $\alpha=5$</em>
    </td>
    <td align="center">
      <img width="300" height="320" alt="Convex_alpha_30" src="https://github.com/user-attachments/assets/66e74b74-2fac-44c2-bdf3-2095e93db607" />
      <em>Convex PF $\alpha=30$</em>
    </td>
  </tr>
</table>


The generated reference vector of Das and dennis based systematic sampling (SS) and the Projected hypercube sampling is depicted here.
<p align="center">
  <img width="320" height="340" alt="SS sampling" src="https://github.com/user-attachments/assets/d490a24e-4b10-4cc4-824f-dda204f7ee44" />
  <img width="320" height="340" alt="PHS sampling" src="https://github.com/user-attachments/assets/f5481449-7d0a-42c1-bd28-2cfc4e317cec" />
</p>
<p align="center">
  <em>Das and Dennis systematic sampling</em> &nbsp;&nbsp;&nbsp;
  <em>Projected hypercube sampling (PHS)</em> &nbsp;&nbsp;&nbsp;
</p>

The comparison studies on multiple alpha parameterized convex and non-convex Pareto fronts shapes with different number of reference points are done using IGD and Coverage error, the result shows that the SS saturates early with increasing reference points while PHS improves continuosly. With increasing alpha, the SS performs poorly while PHS shows less sensitivity to the alpha curvature.

Statistical study on random initilaization of the PHS is done using 31 trials. The result is compared against the SS and the result guaranties that the inference doesn't change with different initialization.

