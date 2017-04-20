# Enron Intent Dataset (Manually Verified)
This is a manually verified version of the Parakweet Labs intent dataset, taken from the Enron email dataset.
It is intended to mark 3655 email "sentences" requiring an action or response from the recipient, or providing significant
information such as future events and deadlines. This has been manually verified by a single individual with focus
on separating business and professional requests from personal/spam. 

Parakweet version:  1929 negative intent, 1726 positive intent.
This version:       2403 negative intent, 1252 positive intent.

## Classification Critera 
Each line has been verified according to the following criteria defining **positive** intent:
1. Requiring a genuine action from the user in imperative or jussive form.
2. Suggestion of a meeting or event in the future.
  * POSITIVE: "There's a party next Friday, we should go" 
  * NEGATIVE: "There was a party last Friday, we should've gone" 
3. Not advertising a service such as technical product, online shopping.
4. Not a comment on a third party matter (not involving the user). 
* POSITIVE: "I need you to finish the report"
* NEGATIVE: "I've asked Amanda to finish the report"
5. Questions not of a casual, vague or rhetorical meaning. 
* In general, these were best classified by judgement of whether such a question required a response or not. For example, "Hope things are well"/"How are you?"/"Was golf good?" would not warrant a reply, whereas "Has the budget situation improved?"/"Was the meeting good?" would. This is, of course, a subjective opinion, but prioritises business contexts over personal.

## Assumptions 
It is also marked by the following assumptions:
1. Any request to click a link is unsolicited unless otherwise explicit:
  * POSITIVE: "Click here to download that report you asked for."
  * NEGATIVE: "Click here to download our latest report."
2. Any action directed towards a name, unless preceeded with a greeting, references a third party individual and is therefore not of interest to the recipient.
 * POSITIVE: "Hi Adam, can you send me the report."
 * NEGATIVE: "Adam can send the report."
3. For the original purpose of this verified dataset, mentions of attachments and cc'd individuals are not of relevance.
 
Given that the criteria can be subjective, some liberty has been taken to judge ambiguous sentences. Therefore there may not be complete
agreement between humans regarding positive/negative intent, however this dataset aims to offer improved accuracy over the original Parakweet Labs release.

## Further Notes
Where noted, some spelling mistakes/typos were also corrected though this is not guaranteed. 

Many "sentences" are short phrases or multiple sentences on one line, but have not been separated for the purpose of verifying data loss between the original and new datasets.

## Sources:
Enron email dataset: https://www.cs.cmu.edu/~./enron/
Parakweet Labs subset with marked intent: https://raw.githubusercontent.com/ParakweetLabs/EmailIntentDataSet/master/src/resources/Ask0729-fixed.txt 



With thanks to Parakweet labs for providing the foundations of this dataset.
