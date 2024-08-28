# Summary
This machine learning project is a classification task. It looks at a dataset containing client information and seeks to predict whether a customer will buy a health insurance product within the next 3 months.

# Dataset Description

## Column Header Descriptions

### General Client Information

- `clntnum`: Unique identifier for the client.
- `race_desc`: Description of the client's race.
- `ctrycode_desc`: Country code indicating the client's location.
- `clttype`: Customer status.
- `stat_flag`: Flag indicating ACTIVE, LAPSED or MATURED. E.g. if there’s at least one inforce policy, then the flag would be ACTIVE. If all of the client’s policies are all lapsed, then it is LAPSED.
- `min_occ_date`: Date of the client's first interaction or policy purchase with the company.
- `cltdob_fix`: Fixed or corrected date of birth of the client.
- `cltsex_fix`: Fixed or corrected gender of the client.

### Client Risk and Status Indicators

- `flg_substandard`: Flag for substandard risk clients.
- `flg_is_borderline_standard`: Flag for borderline standard risk clients.
- `flg_is_revised_term`: Flag if customer ever has revised terms.
- `flg_is_rental_flat`: Indicates if the client lives in a rental flat.
- `flg_has_health_claim`: Flag for clients with health insurance claims.
- `flg_has_life_claim`: Flag for clients with life insurance claims.
- `flg_gi_claim`: Flag for general insurance claims.
- `flg_is_proposal`: Indicates if there is a policy in proposal for client.
- `flg_with_preauthorisation`: Flag for clients with preauthorized transactions or policies.
- `flg_is_returned_mail`: Flag for returned mail instances.

### Client Consent and Communication Preferences

- `is_consent_to_mail`, `is_consent_to_email`, `is_consent_to_call`, `is_consent_to_sms`: Flags indicating client's consent to various forms of communication.
- `is_valid_dm`, `is_valid_email`: Flags indicating the validity of direct mail and email addresses.

### Demographic and Household Information

- `is_housewife_retiree`, `is_sg_pr`, `is_class_1_2`: Flags indicating specific demographics like occupation, residency status, etc.
- `is_dependent_in_at_least_1_policy`: Indicates if the client is a dependent in at least one policy.
- `hh_20`, `pop_20`, `hh_size`, `hh_size_est`: Metrics related to household size and population.
- `annual_income_est`: Estimated annual income of the client, in buckets.

### Policy and Claim History

- `n_months_last_bought_products`, `flg_latest_being_lapse`, `flg_latest_being_cancel`, `recency_lapse`, `recency_cancel`: Metrics related to the recency of policy purchases, lapses, and cancellations.
- `tot_inforce_pols`, `tot_cancel_pols`: Total number of in-force and canceled policies.
- `f_ever_declined_la`: Flag for clients has ever been declined policies.

### Anonymized Insurance Product Metrics (APE, Sum Insured, Prepaid Premiums)

- `ape_`, `sumins_`, `prempaid_*` (e.g., ape_gi_42e115, sumins_ltc_1280bf, prempaid_grp_6fc3e6): Metrics for various anonymized insurance products, likely representing different types of policies like general insurance, long-term care, group policies, etc. The suffixes (like 42e115, 1280bf) are unique identifiers for the specific insurance products. ‘ape’ stands for  Annual Premium Equivalent, 'sumins' for sum insured, ‘prempaid’ stands for premium customers will pay from product inception to product maturity. 

### Other Flags and Metrics

- `f_elx`, `f_mindef_mha`, `f_retail`: Flags possibly related to client's association with specific programs or sectors.
- `flg_affconnect_*`, `affcon_visit_days`, `n_months_since_visit_affcon`: Metrics related to client’s activity in affinity connect.
- `clmcon_visit_days`, `recency_clmcon`, `recency_clmcon_regis`: Metrics related to client’s activity in claim connect.
- `hlthclaim_amt`, `giclaim_amt`, `recency_hlthclaim`, `recency_giclaim`, `hlthclaim_cnt_success`, `giclaim_cnt_success`: Health and general insurance claim-related metrics.
- `flg_hlthclaim_`, `flg_gi_claim_` (e.g., flg_hlthclaim_839f8a_ever, flg_gi_claim_29d435_ever): Flags for specific types of health and general insurance claims, with anonymized identifiers.

### Purchase and Lapse Metrics for Specific Products

- `f_ever_bought_`, `n_months_last_bought_`, `lapse_ape_`, `n_months_since_lapse_` (e.g., f_ever_bought_839f8a, n_months_last_bought_grp_6fc3e6, lapse_ape_ltc_1280bf, n_months_since_lapse_inv_dcd836): Flags and metrics indicating purchase history, lapses, and time since last interaction for various anonymized insurance products.

### Target Column

- `f_purchase_lh`: Flag indicating whether a customer will purchase life or health insurance products within the next three months.
