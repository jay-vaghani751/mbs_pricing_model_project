 # Pricing Agency Mortgage-Backed Security (MBS)

## Objective
This project aims to evaluate whether a given Freddie Mac agency MBS is fairly priced by modeling interest rate paths, simulating borrower prepayments, and calculating expected cash flows.

## Product Description
The analyzed security is a Freddie Mac 30-Year Fixed-Rate MBS (Pool ID: FG G62094), backed by conventional conforming loans. As a pass-through security, it pays monthly principal and interest to investors. It is fully guaranteed by the U.S. government against credit risk, making interest rate and prepayment risk the primary valuation drivers.

## Key MBS Parameters
| Parameter                          | Value                     |
|-----------------------------------|---------------------------|
| Security Type                     | Freddie Mac Gold 30-Year MBS |
| Coupon Rate                       | 5.000%                    |
| WAC / Original WAC                | 5.450% / 5.451%           |
| WAM / Original WAM                | 169 / 186 months          |
| WALA                              | 178 months                |
| Current Factor                    | 0.8424                    |
| Original / Current Balance        | $3.37B / $2.84B           |
| Life CPR                          | 7.4%                      |
| Issue / Maturity Date             | 11/01/2022 – 08/01/2040   |
| Number of Loans                   | 61,897                    |

## Workflow

### 1. Interest Rate Path Simulation
- Generated stochastic interest rate scenarios using models like Vasicek.
- Monthly frequency through the bond's maturity.

### 2. Prepayment Modeling
- Applied PSA model calibrated using Bloomberg CPR history (Life CPR = 7.4).
- Dynamic adjustment of prepayments with interest rate movements.

### 3. Cash Flow Projection
- Calculated monthly payments from scheduled amortization and prepayments.
- Used pass-through mechanics with a 5.0% coupon.

### 4. Valuation and Analysis
- Discounted each path’s cash flows using path-specific interest rates.
- Estimated fair value as the average of simulated values.
- Compared simulated value with Bloomberg quoted price (99-21) to assess pricing fairness.

## Outcome
A valuation framework for analyzing MBS pricing sensitivity to interest rate and prepayment assumptions, helping determine if a security is overvalued or undervalued in the current market to uncover investment opportunities.