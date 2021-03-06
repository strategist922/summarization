# Supervised summarization algorithms

We apply two types of supervised algorithms:
* Domain-independent (Pointer-generator method for Abstractive Summarization)
* Legal domain-specific (Graphical Model and LetSum methods for Extractive Summarization)

## Generated summaries

For the document [sample input.txt](../sample%20input.txt), we describe the summaries generated by each of the methods.

### Pointer-generator

```
$ python parseForExtract.py # for generating the input data for decoding process
$ python make_datafiles_2.py data_dir num_of_datafiles # for generating .bin files to be inputted to model and creating the vocab
$ python run_summarization.py --mode=decode --single_pass=True --data_path=/path/to/chunked/test_* --vocab_path=/path/to/vocab --log_root=/path/to/a/log/directory --exp_name=myexperiment

than this decide first place this interest of than place , merits , shall interested this following deed interest , official , shall intention this rendered this appointed this dacoity this assessee is a partnership concern when income-tax was converted into a limited company this for the assessment year 1947 -48 the assessee claimed that it was entitled to relief under section 25 -lrb- 4 -rrb- of the act as the partnership firm had been succeeded by a private limited company this 15 , payable up .

```

### Graphical Model

```
$ python
>>> import graphicalModel
>>> graphicalModel.get_summary('sample input.txt')
'Where any such claim is made, an assessment shall be made on the basis of the 
income, profits and gains of the said period, and, if an amount of tax has 
already been paid in respect of the income, profits and gains of the previous 
year exceeding the amount payable on the basis of such assessment, a refund 
shall be given of the difference."\n\nThe section does not regard a mere 
change in the personnel of the partners as amounting to succession and 
disregards such a change.In our opinion, this contention is without force.
 It upheld the view taken by the Tribunal.The Tribunal took the view that 
for purposes of income tax the firm was to be regarded as having a separate 
juristic existence apart from the partners carrying on the business and that 
the firm could be carried on even if there was a change in its constitution.\n
It was contended before us that the construction placed by the High Court upon 
section 25(4) of the Act was erroneous and was not warranted by the language of
 the section and that by reason of the change in the composition of the firm 
the same firm did not continue throughout and hence there was no right to 
relief under section 25(4) of the Act in the changed firm.On appeal to the 
Income-tax Tribunal, this decision was reversed and relief was granted to the 
applicant under section 25(4).\nIt was not disputed before the Tribunal that 
the business of the partnership firm of A. W. Figgies & Co. continued as tea 
brokers right from its inception till the time it was succeeded by the limited 
company.The name of the firm was A. W. Figgies & Co., and its\' business was 
that of tea brokers.\nIn 1939 Hillman was brought in and the partnership 
consisted of these three partners.There was a provision in the partnership 
deed of 1939 that on the retirement of any partner the partnership would not 
be determined but would be carried on by the remaining partners.\nFrom the 
statement of the case it does not appear that apart from the mere change in the
 personnel of the partners and in their respective shares there was any actual 
 dissolution of the firm, and any division of its assets and liabilities or a 
 succession to its business by any outside person.\n'
```

### LetSum

``` 
$ python
>>> import letsum
>>> import letsum_test
>>> letsum_test.LetSum('sample input.txt')
'Tribunal case referred question High Court section 66(1) Act : firm 
constituted 31st May, 1947, entitled relief section 25(4) Indian Incometax Act 
25 (4) person Indian Income-tax Act, 1939, carrying business, tax time charged 
provisions Indian Income-tax Act, 1918, succeeded another change merely change 
constitution tax shall payable person respect income, profits gains period end 
previous year person \nassessee partnership changes constitution firm change 
partners.In went share taken Figgies continued 1947, partnership limited 
company.The Commissioner Tribunal held relief section 25(4) Income-tax Act 
given business persons carrying business mere changes constitution firm 
Tribunal view purposes income tax firm existence apart partners carrying 
business firm could carried change view taken us High Court section 25(4) 
Act section change firm firm continue right relief section 25(4) Act section 
regard mere change partners succession true law partnership firm existence 
apart partners name partners true law dissolution firm mere partner consent 
partners person partnership consent firm carry business name till firm charged 
distinct assessable entity distinct partners 3 section partners firm distinct 
assessable firm distinct unit purposes Tribunal High Court right spite mere 
changes constitution business firm constituted continued tea brokers right 
till time succeeded limited company unit carrying business change different 
\n\n\n1926 another partner Squire introduced.In 1932 Figgies went out, 1932 
1939 partnership consisted Notley Squire.In 1939 Hillman brought partnership 
consisted three partners.In 1943 Notley went partnership business carried two 
partners, Squire Hillman.In 1945 Gilbert '
```
