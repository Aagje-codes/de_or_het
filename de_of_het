def de_or_het(noun):
	""" This function takes in a noun and returns the noun with the correct article"""
	noun = noun.lower()

	# we have an excel files saved as csv, that contain words that are definately het-words
	with open('het_woorden.csv', 'r') as csv:
		het_woorden = csv.read().split('\r')

	het_woorden = [w.lower() for w in het_woorden]	

	# and we have an excel file that contains dubious words
	with open('ambiguous_nouns.csv', 'r') as csv:
		ambiguous_nouns = csv.read().split('\r')

	ambiguous_nouns = [w.lower() for w in ambiguous_nouns]	
	message = """\nYour noun may be either a 'de' or a 'het' word. Chosing one or the
other may change the meaning of '{0}'. When in doubt, advice a dictionary.
	"""

	# next we want to see whether our noun is a 'de' or a 'het' noun:
	if noun in ambiguous_nouns:
		raise Exception(message.format(noun))
	elif noun in het_woorden or noun.endswith('je'):
		article = 'het'
	else:
		article = 'de'	
	
	# last, we want the article and the noun returned as one string.	
	return article + " " + noun


if __name__ == '__main__':
	lijstje = ['man', 'vrouw', 'jongen', 'meisje', 'dubbeltje', 'bal']

	for word in lijstje:
		print de_or_het(word)


