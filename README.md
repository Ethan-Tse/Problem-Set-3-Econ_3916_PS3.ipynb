# Problem-Set-3-Econ_3916_PS3.ipynb

Which Number is Right & Why They Differ

Finance’s number ($812$) is correct; the board deck's number ($1,240$) is wrong. Both queries pull from the same warehouse, but they differ by a join. The board query joined customers against orders, duplicating customer rows for those with multiple orders (fan-out bias). Because high-volume customers were counted multiple times, the average was artificially inflated. The correct figure must be computed at the customer level without a 1-to-many join expansion.

Whether the Programme Works

Our causal simulation shows the account-management programme has a small, positive effect, but the naive comparison overstated its success because it was confounded by existing account size. Furthermore, controlling for downstream metrics like support tickets introduces collider bias, which distorts estimates and makes conclusions less reliable.

Pre-Slide Recommendations

To prevent this from happening again before any number hits a board deck, we recommend the analytics team institute two mandatory checks:

Automated Unit-of-Observation Guardrails: Implement review scripts that automatically flag any aggregate or average taken over a fanned-out join result.

Mandatory Peer Code Review: Require all metrics involving multi-table joins to be audited against base table row counts to ensure denominators remain uncompromised before publication.
