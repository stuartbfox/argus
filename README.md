# Argus
Argus is a new way of thinking about systems monitoring.
Systems monitoring is much more than disk space, cpu load, api responsiveness.
It's all about what the customer sees. 

For example :-
1) Your public api times out when clients access it. Your internal monitoring system is green. Is the whole system healthy?
Obviously the answer is no and remediation needs to be started immediately.

2) Your public api is responding within normal tolerances. Your internal monitoring system is red, you just lost 7 of your 21 cassandra nodes.
Remediation can probably wait

3) Predictor says you will run out of capacity in 6 months
Not a show stopper, start the ordering process

4) Predictor says you will run out of stuff in 3 days
A show stopper unless averted.
Could, in theory be passed to Reator to create 100 new cassandra nodes in 2 days time

# Components
## Agent
Runs on the target system
## Proxy
Forms a limited size mesh (n5) to ensure systems data is delivered to the Messenger
## Messenger
AMQP server
## Observer
Detects failures and triggers a reaction
## Predictor
Predictive analyser
## Reactor
Reacts to triggers from either Observer and Predictor (or anywhere supplying enough information to carry out an action)
