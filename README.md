import string
i=string.punctuation+string.whitespace
def processbook(fn): #fn will be filename of the book 
	book=open(fn)
	lst=[]
	hist={}
	for line in book:    #WILL GET THE LINE IN THE BOOK
		for word in line.split():  #will split each word with space
			word=word.strip(i)
			word=word.lower()
			#print(word)
			#lst.append(word)
			hist[word]=hist.get(word,0)+1
#			if word in hist:
#				hist[word]+=1
#			else:
#				hist[word]=1
	#print(len(lst))
	print(hist)
	print('total no of words',sum(hist.values())) #give sum of all values sum is built in function
	print('unique words:',len(hist.keys()))

	for key,value in hist.items():   #this will store keys and values in a lst as tuplee because append only take 1 arg
		lst.append((value,key))
	print(lst)
	lst.sort(reverse=True) #sorts the lst from low to high so reverse is passed for high to low
	print("top 20 freq words:",lst[:20])
	for count,word in lst[:20]:
		print("top 20 words:",word) #only print words not the count as before
processbook('pract.txt')



"""
lst=[(count,word) for word,count in hist.items()]
"""
