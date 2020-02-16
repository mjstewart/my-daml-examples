https://docs.daml.com/daml/intro/6_Parties.html

a transaction is

a tree of transactions, or a forest of actions.
Each transaction is made up of a list of actions. Each action has a child transaction called its consequences.


Each action has a set of required authorizers – the parties that must authorize that action.
Each transaction has a set of authorizers – the parties that did actually authorize the transaction.

The authorization rule is that the required authorizers of every action are a subset of the authorizers of the parent transaction.

The required authorizers of actions are:

The required authorizers of an exercise action are the controllers on the corresponding choice. Remember that Archive and archive are just an implicit choice with the signatories as controllers.

The required authorizers of a create action are the signatories of the contract.

The required authorizers of a fetch action (which also includes fetchByKey) are somewhat dynamic and covered later.


The authorizers of transactions are:

The root transaction of a commit is authorized by the submitting party.
The consequences of an exercise action are authorized by the actors of that action plus the signatories of the contract on which the action was taken.
