#Python Cookbook review



**P2**——Unpacking actually works with any object that happens to be <u>iterable</u>, not just tuples or

lists. This includes strings, files, iterators, and generators.						

- **Module**: <P6> *collections*.deque</P6>, *collections*.defaultdict，*collections*.OrderedDict, *collections*.Count, 

  ​		<p30>*collections*.namedtuple</p30>, <p34>*collections*.ChainMap</p34>

  ​	Methods: dict.setdefault( ), Count.most_common( ), <p31>_replace()</p31>, <p35>new_child( )</p35>

  ​	**Hints**:

  ​		**( About defaultdict )** A feature of defaultdict is that it automatically initializes the first value so

  ​						you can simply focus on adding items.

  ​		**( About ALL dict )** A little-known feature of

  ​						keys views is that they also support common set operations such as unions, 						intersections, and differences.

  ​		**( About Counter )** Counter instances is that they can be easily combined using

  ​						various mathematical operations.

  ​		**( About ChainMap )** If there are duplicate keys, the values from the first mapping get used.

  

- **Module**: heapq

  ​	Method: <P7>nlargestI( ), nsmallest( )</P7>,<P8> heapq.heapify( ), heapq.heappop( )</p8> 

  ​	**Hints**: **!r** choose <u>rept</u> to format the value while **!s** choose <u>str</u> 

  

- **Module**: operator.itemgetter, operator.attrgetter

  

- **Module**: <p25>itertools.groupby( )</p25>,<p28> itertools.compress( )</p28>

  ​	**Hints**: 

  ​		**( About groupby( ) )** groupby( ) only examines consecutive items

- **Module**: os.listdir( ), os.get_terminal_size( ){ columns, rows } 

- **Module**: <p40>**re**</p40>

  ​	Method: re.match( ),  re.compile, re.findall, re.finditer, <p45>re.sub</p45>, re.replace, re.subn, 

  ​		<p67>re.scanner</p67>

  ​	Hints:

  ​		**( About startwith and endwith )**<p39> If you need to check against multiple choices, simply provide a 			tuple of possibilities to startswith() or endswith(), Oddly, this is one part of Python where a tuple is 			actually required as input. If you happen to have the choices specified in a list or set, just make sure 			you convert them using tuple() first</p39>

  ​		**( A pattern )** $

  ​		**( Some arguments )** re.IGNORECASE, re.DOTALL

  ​		**( A formule )**The * operator in a regular expression is greedy, so matching is based on finding the longest 			possible match. To fix this, add the ? modifier after the * operator in the pattern )

  ​		**( ?P\<TOKENNAME> )**: In these re patterns, *?P<>*  convention is used to assign a name to the pattern.  

- Module

- Method:  **zip( )**

  ​	Hints: zip( ) creates an iterator that can only beconsumed once.

- Method: **slice( )** { slice.start, slice.stop, slice.step }, **indices( )**

- Method: <p27>filter( )</p27>

- Method: <p32>any( )</p32>

- Method: <p35>merged.update( )</p35>

- Method: <p39>urllib.request.urlopen</p39>

- Method: <p40>fnmatch.fnmatch, rematch.fnmatchcase</p40>

- Method: <p46>calendar.month_abbr</p46>

- Method: <p51>unicodedata.normalize, unicodedata.combining</p51>

- Method: <p55>translate, dict.fromkeys</p51>

- Method: str.encode, str.decode

  ​	Hints: 

  ​		( Some arguments ) errors='xmlcharrefreplace'

- Method: str.ljust, str.rjust, str.center, format

- Hint: The *sep* argument of method *print*

- **Method**: str.format_map

- Method: <p63>string.Template( ), string.substitude( )</p63>

- **Hints**: <p63>Parts of this recipe also illustrate a few interesting advanced features. The little-known

  ​		\__missing__( ) method of mapping/dict classes is a method that you can define to

  ​		handle missing values. In the safesub class, this method has been defined to return

  ​		missing values back as a placeholder. Instead of getting a KeyError exception, you

  ​		would see the missing values appearing in the resulting string (potentially useful for

  ​		debugging).

  ​		The sub() function uses sys._getframe(1) to return the stack frame of the caller. From

  ​		that, the f_locals attribute is accessed to get the local variables. It goes without saying

  ​		that messing around with stack frames should probably be avoided in most code. However,

  ​		for utility functions such as a string substitution feature, it can be useful. As an

  ​		aside, it’s probably worth noting that f_locals is a dictionary that is a copy of the local

  ​		variables in the calling function. Although you can modify the contents of f_locals,the modifications don’t 		actually have any lasting effect. Thus, even though accessing a

  ​		different stack frame might look evil, it’s not possible to accidentally overwrite variables

  ​		or change the local environment of the caller.</p63>

- Module: decimal.Decimal

  ​	Method: <p85>decimal.localcontext( )</p85>

- **Module**: struct

  ​	Method: struct.unpack( )

- Method: textwrap.fill( )

- Method: html.escape( ), <p66>html.parser.HTMLParser( ), xml.sax.saxutils.unescape( ),

  ​		xml.etree.ElementTree</p66>

- **Source Code**: p71-74, Writing a Simple Recursive Descent Parser

- Module: <p76>ply.lex.lex, ply.yacc.yacc</p76>, <p78>ast</p78>

- Method: <p79>bytearray </p79>

- Method: math.fsum( )

- Method: int.from_bytes( ), int.to_bytes( )

  **Endianness**:  The order of read data is from the lower bits to higher bits

  ![image-20190310181534714](/Users/Stori/Library/Application Support/typora-user-images/image-20190310181534714.png)



