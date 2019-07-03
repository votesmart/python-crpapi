#python-crpapi


Python library for interacting with the CRP API.

Based on python-sunlightapi, a project of Sunlight Labs (c) 2008.  
Written by James Turk <jturk@sunlightfoundation.com>.

All code is under a BSD-style license, see LICENSE for details.


##Requirements

python >= 2.4

simplejson >= 1.8 (not required with python 2.6, will use built in json module)


##Installation

To install via `pipenv`:

`pipenv install -e git+https://github.com/votesmart/python-crpapi.git#egg=python-crpapi `


To install run
```
    python setup.py install
```
which will install the bindings into python's site-packages directory.

##Usage

To initialize the api, all that is required is for it to be imported and for an
API key to be defined.

(If you do not have an API key visit http://www.opensecrets.org/api/admin/ to
register for one.)

Import modules:
```    
    >>> from crpapi import CRP, CRPApiError
```
    
And set your API key:
```    
    >>> CRP.apikey = 'yr-api-key'
```

See below for specific method usage. Full documentation of the methods is located here: https://www.opensecrets.org/resources/create/api_doc.php
	

##Methods

###Member Methods:

#####getLegislators
```
>>> print CRP.getLegislators.get(id='NJ04')
[{u'@attributes': {u'website': u'http://chrissmith.house.gov', u'fax': u'202-225-7768', u'birthdate': u'1953-03-04', u'office': u'NJ04', u'cid': u'N00009816', u'twitter_id': u'', u'lastname': u'SMITH', u'feccandid': u'H8NJ04014', u'webform': u'http://chrissmith.house.gov/zipauth.html', u'exit_code': u'0', u'comments':u'',u'firstlast': u'Chris Smith', u'phone': u'202-225-3765', u'facebook_id': u'', u'first_elected': u'1980', u'congress_office': u'2373 Rayburn HouseOffice Building', u'gender': u'M', u'party': u'R', u'youtube_url': u'http://youtube.com/USRepChrisSmith', u'bioguide_id': u'S000522', u'votesmart_id':u'26952'}}, {u'@attributes': {u'website': u'http://menendez.senate.gov', u'fax': u'202-228-2197',u'birthdate': u'1954-01-01', u'office': u'NJS1',u'cid': u'N00000699', u'twitter_id': u'SenatorMenendez', u'lastname': u'MENENDEZ', u'feccandid': u'H2NJ13075',u'webform': uhttp://menendez.senate.gov/contact', u'exit_code': u'0', u'comments': u'', u'firstlast': u'Robert Menendez', u'phone': u'202-224-4744', u'facebook_id': u'senatormenendez', u'first_elected': u'2006',u'congress_office': u'528Hart Senate Office Building', u'gender': u'M', u'party': u'D', u'youtube_url': u'http://youtube.com/SenatorMenendezNJ',u'bioguide_id': u'M000639', u'votesmart_id': u'26961'}}, {u'@attributes': {u'website': u'http://www.lautenberg.senate.gov', u'fax': u'202-228-4054', u'birthdate':u'1924-01-23', u'office': u'NJS2', u'cid': u'N00000659', u'twitter_id': u'franklautenberg', u'lastname': u'LAUTENBERG', u'feccandid': u'S2NJ00080',u'webform': u'http://www.lautenberg.senate.gov/contact/routing.cfm', u'exit_code': u'1', u'comments': u'Died on June 3, 2013', u'firstlast': u'FrankLautenberg', u'phone': u'202-224-3224', u'facebook_id': u'franklautenberg', u'first_elected': u'2002', u'congress_office': u'324 Hart Senate Office Building',u'gender': u'M', u'party': u'D', u'youtube_url': u'http://youtube.com/franklautenberg', u'bioguide_id': u'L000123', u'votesmart_id': u'53324'}},{u'@attributes': {u'website': u'', u'fax': u'', u'birthdate': u'', u'office': u'NJS2', u'cid': u'N00035267', u'twitter_id': u'', u'lastname': u'BOOKER', u'feccandid': u'', u'webform': u'', u'exit_code': u'0', u'comments': u'Elected in special on 10/17/2013', u'firstlast': u'Cory Booker', u'phone': u'', u'facebook_id': u'', u'first_elected': u'2013', u'congress_office': u'', u'gender': u'M', u'party': u'D', u'youtube_url': u'', u'bioguide_id': u'', u'votesmart_id':u''}}]
```
#####memPFDprofile
```
>>> print CRP.memPFDprofile.get(cid='N00007364',year='2010')
{u'@attributes': {u'origin': u'Center for Responsive Politics', u'tx_low': u'1658021', u'asset_high': u'95707022', u'transaction_count': u'21', u'name': u'Feinstein,Dianne', u'update_timestamp': u'6/6/13', u'net_high': u'93707020', u'net_low': u'44386225', u'data_year': u'2010', u'source': u'http://www.opensecrets.org/pfds/CIDSummary.php?CID=N00007364&year=2010', u'tx_high': u'2620001', u'member_id': u'N00007364', u'positions_held_count': u'0',u'asset_low': u'46386227', u'asset_count': u'137'}, u'assets': {u'asset': [{u'@attributes': {u'sector': u'Misc Business', u'name': u'Carlton Hotel Properties',u'industry': u'Lodging/Tourism', u'holdings_low': u'5000001', u'subsidiary_of': u'', u'holdings_high': u'25000000'}}, {u'@attributes': {u'sector':u'Finance/Insur/RealEst', u'name': u'CB Richard Ellis', u'industry': u'Real Estate', u'holdings_low': u'3130012', u'subsidiary_of': u'CBRE Holding',u'holdings_high': u'5453001'}}, {u'@attributes': {u'sector': u'Finance/Insur/RealEst', u'name': u'Condominium/Princeville, Kauai-Hawaii', u'industry':u'RealEstate', u'holdings_low': u'1000001', u'subsidiary_of':u'', u'holdings_high': u'5000000'}}, {u'@attributes': {u'sector': u'Unknown', u'name':u'Dianne Feinstein 1991 Blind Trust', u'industry': u'Unknown', u'holdings_low': u'1000001', u'subsidiary_of': u'', u'holdings_high': u'5000000'}}, {u'@attributes': {u'sector': u'Other', u'name': u'Career Education Corp', u'industry': u'Education', u'holdings_low': u'2165010', u'subsidiary_of': u'', u'holdings_high': u'4551000'}}]}, u'transactions': {u'transaction': [{u'@attributes': {u'asset_name': u'JPMorgan Chase & Co', u'tx_date': u'Dec  3 2010',u'value_high': u'1000001', u'value_low': u'1000001', u'tx_action': u'Purchased'}}, {u'@attributes': {u'asset_name': u'Vanguard Life Strategy Income Fund',u'tx_date': u'Jul 15 2010', u'value_high': u'500000', u'value_low': u'250001', u'tx_action': u'Purchased'}}, {u'@attributes': {u'asset_name': u'Vanguard LifeStrategy Conservative Grw', u'tx_date': u'Jul 15 2010', u'value_high': u'500000', u'value_low': u'250001', u'tx_action': u'Purchased'}}, {u'@attributes':{u'asset_name': u'Franklin Small Mid Cap Growth Fund', u'tx_date': u'Aug 31 2010', u'value_high': u'50000', u'value_low': u'15001', u'tx_action':u'Sold'}}, {u'@attributes': {u'asset_name': u'JHT International Value', u'tx_date': u'Aug 27 2010', u'value_high': u'50000', u'value_low': u'15001',u'tx_action': u'Purchased'}}]}}
```

###Candidate Methods:

#####candSummary
```    
>>> print CRP.candSummary.get(cid='N00007360',cycle='2014')
{u'origin': u'Center for Responsive Politics', u'next_election': u'2014', u'debt': u'0', u'last_updated': u'12/31/2013', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'spent': u'1304840.24', u'chamber': u'H', u'state': u'CA', u'first_elected': u'1987', u'source': u'http://www.opensecrets.org/politicians/summary.php?cid=N00007360&cycle=2014', u'party': u'D', u'total': u'1294719.87', u'cash_on_hand': u'439206.96', u'cycle':u'2014'}
```
		
#####candContrib:
```
>>> print CRP.candContrib.get(cid='N00007360',cycle='2014')
{u'origin': u'Center for Responsive Politics', u'next_election': u'2014', u'debt': u'0', u'last_updated': u'12/31/2013', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'spent': u'1304840.24', u'chamber': u'H', u'state': u'CA', u'first_elected': u'1987', u'source': u'http://www.opensecrets.org/politicians/summary.php?cid=N00007360&cycle=2014', u'party': u'D', u'total': u'1294719.87', u'cash_on_hand': u'439206.96', u'cycle':u'2014'}>>> print CRP.candContrib.get(cid='N00007360',cycle='2014')[{u'@attributes': {u'org_name': u'Certain Software Inc', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Chartwell Hotels', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Jewish Community Federation', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Marcus & Millichap', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Stanford University', u'total': u'10400'}}, {u'@attributes': {u'org_name': u'Facebook Inc', u'total': u'10200'}}, {u'@attributes': {u'org_name': u'American Assn for Justice', u'total': u'10000'}},{u'@attributes': {u'org_name': u'American Health Care Assn', u'total': u'10000'}}, {u'@attributes': {u'org_name': u'Boeing Co', u'total': u'10000'}},{u'@attributes': {u'org_name': u'Francisco Partners', u'total': u'10000'}}]
```

#####candIndustry:
```
>>> print CRP.candIndustry.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'74750', u'industry_code': u'H01', u'industry_name': u'Health Professionals', u'pacs': u'70500', u'indivs': u'4250'}}, {u'@attributes':{u'total': u'62500', u'industry_code': u'K01', u'industry_name': u'Lawyers/Law Firms', u'pacs': u'21500', u'indivs': u'41000'}}, {u'@attributes':{u'total': u'51200', u'industry_code': u'F10', u'industry_name': u'Real Estate', u'pacs': u'27500', u'indivs': u'23700'}}, {u'@attributes':{u'total':u'50600', u'industry_code': u'B12', u'industry_name': u'Computers/Internet', u'pacs': u'25000', u'indivs': u'25600'}}, {u'@attributes':{u'total': u'45000', u'industry_code': u'P01', u'industry_name': u'Building Trade Unions', u'pacs': u'45000', u'indivs':u'0'}}, {u'@attributes':{u'total': u'39250', u'industry_code': u'F07', u'industry_name': u'Securities & Investment', u'pacs': u'16000', u'indivs': u'23250'}},{u'@attributes': {u'total': u'39000', u'industry_code': u'H02', u'industry_name': u'Hospitals/Nursing Homes', u'pacs': u'35000', u'indivs': u'4000'}},{u'@attributes': {u'total': u'38000', u'industry_code': u'P04', u'industry_name': u'Public Sector Unions', u'pacs': u'38000', u'indivs': u'0'}},{u'@attributes': {u'total': u'37900', u'industry_code': u'B02', u'industry_name': u'TV/Movies/Music', u'pacs': u'14500', u'indivs': u'23400'}},{u'@attributes': {u'total': u'35800', u'industry_code': u'F13', u'industry_name': u'Misc Finance', u'pacs': u'0', u'indivs': u'35800'}}]
```

#####candIndByInd:
```
>>> print CRP.candIndByInd.get(cid='N00007360',cycle='2014',ind='H01')
{u'origin': u'Center for Responsive Politics', u'last_updated': u'2/18/14', u'cand_name': u'Pelosi, Nancy', u'cid': u'N00007360', u'industry': u'Health Professionals', u'pacs': u'70500', u'rank': u'36', u'indivs': u'4250', u'chamber': u'H', u'state': u'California', u'source': uhttp://www.opensecrets.org/industries/recips.php?Ind=H01&cycle=2014&recipdetail=H&Mem=Y&sortorder=U', u'party': u'D', u'total': u'74750', u'cycle': u'2014'}
```

#####candSector:
```
>>> print CRP.candSector.get(cid='N00007360',cycle='2014')
[{u'@attributes': {u'total': u'11000', u'indivs': u'0', u'sectorid': u'A', u'pacs': u'11000', u'sector_name': u'Agribusiness'}}, {u'@attributes': {u'total': u'104900', u'indivs': u'59400', u'sectorid': u'B', u'pacs': u'45500', u'sector_name': u'Communic/Electronics'}}, {u'@attributes': {u'total': u'15800', u'indivs': u'9800', u'sectorid': u'C', u'pacs': u'6000', u'sector_name': u'Construction'}},{u'@attributes': {u'total': u'24000', u'indivs': u'0', u'sectorid': u'D', u'pacs':u'24000', u'sector_name': u'Defense'}}, {u'@attributes': {u'total': u'5500',u'indivs': u'0', u'sectorid': u'E', u'pacs': u'5500', u'sector_name': u'Energy/Nat Resource'}}, {u'@attributes': {u'total': u'154500', u'indivs': u'84000', u'sectorid': u'F', u'pacs': u'70500', u'sector_name':u'Finance/Insur/RealEst'}}, {u'@attributes': {u'total': u'126500', u'indivs': u'8500', u'sectorid': u'H', u'pacs': u'118000', u'sector_name':u'Health'}}, {u'@attributes': {u'total': u'73600', u'indivs': u'52100', u'sectorid': u'K', u'pacs': u'21500', u'sector_name': u'Lawyers &Lobbyists'}},{u'@attributes': {u'total': u'21000', u'indivs': u'0', u'sectorid': u'M', u'pacs': u'21000', u'sector_name': u'Transportation'}}, {u'@attributes':{u'total': u'82900', u'indivs': u'67400', u'sectorid': u'N', u'pacs': u'15500', u'sector_name': u'Misc Business'}}, {u'@attributes': {u'total': u'165500', u'indivs': u'0', u'sectorid': u'P', u'pacs': u'165500', u'sector_name': u'Labor'}}, {u'@attributes': {u'total': u'67030', u'indivs': u'36680', u'sectorid': u'Q', u'pacs': u'30350', u'sector_name': u'Ideology/Single-Issue'}}, {u'@attributes': {u'total': u'65850', u'indivs': u'63850', u'sectorid': u'W',u'pacs': u'2000', u'sector_name': u'Other'}}]
```

###Organization Methods:

#####getOrgs
```
>>> print CRP.getOrgs.get(org='Goog')
[{u'@attributes': {u'orgname': u'Googasian Firm', u'orgid': u'D000051419'}}, {u'@attributes': {u'orgname': u'Google Inc', u'orgid': u'D000022008'}}]
```

#####orgSummary
```
>>> print CRP.orgSummary.get(id='D000022008')
{u'@attributes': {u'gave_to_party': u'394046', u'gave_to_pac': u'215000', u'pacs': u'381500', u'orgname': u'Google Inc', u'gave_to_cand': u'680409', u'source':u'www.opensecrets.org/orgs/summary.php?id=D000022008', u'repubs': u'481717', u'indivs': u'667655', u'lobbying': u'15800000', u'outside': u'0', u'orgid':u'D000022008', u'dems': u'715598', u'mems_invested': u'25', u'total': u'1424019', u'soft': u'220500', u'tot527': u'154364', u'gave_to_527': u'154364',u'cycle': u'2014'}}
```

###Committee Methods:

#####congCmteIndus
```
>>> print CRP.congCmteIndus.get(indus='F10',cmte='HARM')
[{u'@attributes': {u'cid': u'N00024753', u'pacs': u'9500', u'indivs': u'81800',u'state': u'Colorado', u'member_name': u'Coffman, Mike', u'party': u'R', u'total':u'91300'}}, {u'@attributes': {u'cid': u'N00031244', u'pacs': u'12500', u'indivs': u'36300', u'state': u'Nevada', u'member_name': u'Heck, Joe', u'party': u'R', u'total': u'48800'}}, {u'@attributes': {u'cid': u'N00030962', u'pacs': u'4500', u'indivs': u'40150', u'state': u'Virginia', u'member_name': u'Rigell, Scott',u'party': u'R', u'total': u'44650'}}, {u'@attributes': {u'cid': u'N00025881', u'pacs': u'2000', u'indivs': u'41200', u'state': u'Hawaii', u'member_name': u'Hanabusa, Colleen', u'party': u'D', u'total': u'43200'}}, {u'@attributes': {u'cid':u'N00033591', u'pacs': u'6000', u'indivs': u'37000', u'state': u'California', u'member_name': u'Peters, Scott', u'party': u'D', u'total': u'43000'}}, {u'@attributes': {u'cid': u'N00031005', u'pacs': u'0', u'indivs': u'36050', u'state': u'Missouri', u'member_name': u'Hartzler, Vicky', u'party': u'R', u'total': u'36050'}}, {u'@attributes': {u'cid': u'N00033839', u'pacs': u'10000', u'indivs': u'22650', u'state': u'Texas', u'member_name': u'Veasey, Marc', u'party': u'D', u'total': u'32650'}}, {u'@attributes': {u'cid': u'N00004436', u'pacs': u'7000', u'indivs': u'24550', u'state': u'Minnesota', u'member_name': u'Kline, John', u'party': u'R', u'total': u'31550'}}, {u'@attributes': {u'cid': u'N00030768', u'pacs':u'3000', u'indivs': u'28250', u'state': u'Alabama', u'member_name': u'Roby, Martha', u'party': u'R', u'total': u'31250'}}, {u'@attributes': {u'cid':u'N00029026', u'pacs': u'2000', u'indivs': u'27500', u'state': u'Massachusetts', u'member_name': u'Tsongas, Niki', u'party': u'D', u'total': u'29500'}},{u'@attributes': {u'cid': u'N00032022', u'pacs': u'6500', u'indivs': u'20250', u'state': u'South Dakota', u'member_name': u'Noem, Kristi', u'party': u'R',u'total': u'26750'}}, {u'@attributes': {u'cid': u'N00013770', u'pacs': u'11500', u'indivs': u'13500', u'state': u'Pennsylvania', u'member_name': u'Shuster,Bill', u'party': u'R', u'total': u'25000'}}, {u'@attributes': {u'cid': u'N00008274', u'pacs': u'2000', u'indivs': u'21440', u'state': u'California',u'member_name': u'Sanchez, Loretta', u'party': u'D', u'total': u'23440'}}, {u'@attributes': {u'cid': u'N00013799', u'pacs': u'2000', u'indivs':u'19800', u'state': u'Virginia', u'member_name': u'Forbes, Randy', u'party': u'R', u'total': u'21800'}}, {u'@attributes': {u'cid': u'N00033981', u'pacs':u'4000', u'indivs': u'17750', u'state': u'Arizona', u'member_name': u'Barber, Ron', u'party': u'D', u'total': u'21750'}}, {u'@attributes': {u'cid':u'N00033310', u'pacs': u'10000', u'indivs': u'11350', u'state': u'Ohio', u'member_name': u'Wenstrup, Brad', u'party': u'R', u'total': u'21350'}}, {u'@attributes': {u'cid': u'N00027891', u'pacs': u'5000', u'indivs': u'16000', u'state': u'New York', u'member_name': u'Maffei, Dan', u'party': u'D', u'total':u'21000'}}, {u'@attributes': {u'cid': u'N00029679', u'pacs': u'1000', u'indivs': u'18350', u'state': u'Louisiana', u'member_name': u'Fleming, John',u'party': u'R', u'total': u'19350'}}, {u'@attributes': {u'cid': u'N00029649', u'pacs': u'1000', u'indivs': u'18220', u'state': u'California', u'member_name':u'Speier, Jackie', u'party': u'D', u'total': u'19220'}}, {u'@attributes': {u'cid': u'N00024759', u'pacs': u'8390', u'indivs': u'10750', u'state':u'Alabama', u'member_name': u'Rogers, Mike D', u'party': u'R', u'total': u'19140'}}, {u'@attributes': {u'cid': u'N00033316', u'pacs': u'6000', u'indivs':u'12934', u'state': u'Texas', u'member_name': u'Castro, Joaquin', u'party': u'D', u'total': u'18934'}}, {u'@attributes': {u'cid': u'N00003132', u'pacs':u'2000', u'indivs': u'16600', u'state': u'Tennessee', u'member_name': u'Cooper, Jim', u'party': u'D', u'total': u'18600'}}, {u'@attributes': {u'cid':u'N00025175', u'pacs': u'12000', u'indivs': u'6550', u'state': u'Ohio', u'member_name': u'Turner, Michael R', u'party': u'R', u'total': u'18550'}},{u'@attributes': {u'cid': u'N00029258', u'pacs': u'11000', u'indivs': u'7200', u'state': u'California', u'member_name': u'Hunter, Duncan D', u'party': u'R', u'total': u'18200'}}, {u'@attributes': {u'cid': u'N00034453', u'pacs': u'8000', u'indivs': u'9550', u'state': u'Washington', u'member_name': u'Kilmer, Derek',u'party': u'D', u'total': u'17550'}}, {u'@attributes': {u'cid': u'N00030856', u'pacs': u'2000', u'indivs': u'14885', u'state': u'California', u'member_name':u'Garamendi, John', u'party': u'D', u'total': u'16885'}}, {u'@attributes': {u'cid': u'N00034224', u'pacs': u'1000', u'indivs': u'14850', u'state':u'California', u'member_name': u'Cook, Paul', u'party': u'R', u'total': u'15850'}}, {u'@attributes': {u'cid': u'N00032457', u'pacs': u'4890', u'indivs':u'10350', u'state': u'Georgia', u'member_name': u'Scott, Austin', u'party': u'R', u'total': u'15240'}}, {u'@attributes': {u'cid': u'N00031226', u'pacs':u'7000', u'indivs': u'8200', u'state': u'Indiana', u'member_name': u'Walorski, Jackie', u'party': u'R', u'total': u'15200'}}, {u'@attributes': {u'cid':u'N00007833', u'pacs': u'3500', u'indivs': u'9150', u'state': u'Washington', u'member_name': u'Smith, Adam', u'party': u'D', u'total': u'12650'}},{u'@attributes': {u'cid': u'N00006052', u'pacs': u'2000', u'indivs': u'9950', u'state': u'Texas', u'member_name': u'Thornberry, Mac', u'party': u'R',u'total': u'11950'}}, {u'@attributes': {u'cid': u'N00026041', u'pacs': u'5000', u'indivs': u'6850', u'state': u'Texas', u'member_name':u'Conaway, Mike',u'party': u'R', u'total': u'11850'}}, {u'@attributes': {u'cid': u'N00033541', u'pacs': u'8000', u'indivs': u'3800', u'state': u'Texas', u'member_name':u'Gallego, Pete', u'party': u'D', u'total': u'11800'}}, {u'@attributes': {u'cid': u'N00031998', u'pacs': u'2000', u'indivs': u'9704', u'state': u'NewYork', u'member_name': u'Gibson, Chris', u'party': u'R', u'total': u'11704'}}, {u'@attributes': {u'cid': u'N00029459', u'pacs': u'3000', u'indivs': u'8500', u'state': u'Virginia', u'member_name': u'Wittman, Rob', u'party': u'R', u'total': u'11500'}}, {u'@attributes': {u'cid': u'N00002299', u'pacs': u'2000', u'indivs':u'9100', u'state': u'North Carolina', u'member_name': u'Jones, Walter B Jr', u'party': u'R', u'total': u'11100'}}, {u'@attributes': {u'cid': u'N00027860',u'pacs': u'5500', u'indivs': u'5500', u'state': u'Illinois', u'member_name': u'Duckworth, Tammy', u'party': u'D', u'total': u'11000'}}, {u'@attributes':{u'cid': u'N00002356', u'pacs': u'2000', u'indivs': u'8000', u'state': u'North Carolina', u'member_name': u'McIntyre, Mike', u'party': u'D',u'total':u'10000'}}, {u'@attributes': {u'cid': u'N00027741', u'pacs': u'2000', u'indivs': u'7100', u'state': u'Iowa', u'member_name': u'Loebsack, David',u'party': u'D', u'total': u'9100'}}, {u'@attributes': {u'cid': u'N00024842', u'pacs': u'2500', u'indivs': u'6500', u'state': u'Connecticut', u'member_name':u'Courtney, Joe', u'party': u'D', u'total': u'9000'}}, {u'@attributes': {u'cid': u'N00029513', u'pacs': u'3500', u'indivs': u'5250', u'state':u'Indiana', u'member_name': u'Carson, Andre', u'party':u'D', u'total': u'8750'}}, {u'@attributes': {u'cid': u'N00031988', u'pacs': u'2000', u'indivs':u'6600', u'state': u'New Jersey', u'member_name': u'Runyan, Jon', u'party': u'R', u'total': u'8600'}}, {u'@attributes': {u'cid': u'N00009724', u'pacs':u'4000', u'indivs': u'4050', u'state': u'Rhode Island', u'member_name':u'Langevin, Jim', u'party': u'D', u'total': u'8050'}}, {u'@attributes': {u'cid': u'N00028091', u'pacs': u'0', u'indivs': u'7800', u'state': u'New Hampshire', u'member_name': u'Shea-Porter, Carol', u'party': u'D', u'total': u'7800'}}, {u'@attributes': {u'cid': u'N00000851', u'pacs': u'2000', u'indivs': u'5250', u'state': u'New Jersey', u'member_name': u'LoBiondo, Frank A', u'party': u'R', u'total': u'7250'}}, {u'@attributes': {u'cid': u'N00024809', u'pacs': u'3000', u'indivs': u'4000', u'state': u'South Carolina', u'member_name': u'Wilson, Joe',u'party': u'R', u'total': u'7000'}}, {u'@attributes': {u'cid': u'N00034884', u'pacs': u'3000', u'indivs': u'2550', u'state': u'Illinois', u'member_name': u'Enyart, William',u'party': u'D', u'total': u'5550'}}, {u'@attributes': {u'cid': u'N00027848', u'pacs': u'5000', u'indivs': u'0', u'state': u'Georgia', u'member_name': u'Johnson, Hank', u'party': u'D', u'total': u'5000'}}, {u'@attributes': {u'cid': u'N00009604', u'pacs': u'1000', u'indivs': u'3500', u'state': u'California', u'member_name': u'Davis, Susan A', u'party': u'D', u'total': u'4500'}}, {u'@attributes': {u'cid': u'N00000826', u'pacs': u'3000', u'indivs': u'1500', u'state':u'New Jersey', u'member_name': u'Andrews, Robert E', u'party': u'D', u'total': u'4500'}}, {u'@attributes': {u'cid': u'N00001619', u'pacs': u'1000', u'indivs': u'3250', u'state': u'Pennsylvania', u'member_name': u'Brady, Robert A', u'party': u'D',u'total': u'4250'}}, {u'@attributes': {u'cid': u'N00013846', u'pacs': u'2000', u'indivs': u'2000', u'state': u'Florida', u'member_name': u'Miller, Jeff', u'party': u'R', u'total': u'4000'}}, {u'@attributes': {u'cid': u'N00006882', u'pacs':u'3500', u'indivs': u'0', u'state': u'California', u'member_name': u'McKeon, Buck', u'party': u'R', u'total': u'3500'}}, {u'@attributes': {u'cid':u'N00031958', u'pacs': u'2000', u'indivs': u'1250', u'state': u'Mississippi', u'member_name': u'Palazzo, Steven', u'party': u'R', u'total': u'3250'}},{u'@attributes': {u'cid': u'N00028133', u'pacs': u'2500', u'indivs': u'750', u'state': u'Colorado', u'member_name': u'Lamborn, Douglas L', u'party': u'R',u'total': u'3250'}}, {u'@attributes': {u'cid': u'N00033532', u'pacs': u'0', u'indivs': u'2300', u'state': u'Oklahoma', u'member_name': u'Bridenstine, James',u'party': u'R', u'total': u'2300'}}, {u'@attributes': {u'cid': u'N00030910', u'pacs': u'2000', u'indivs': u'0', u'state': u'Alabama', u'member_name':u'Brooks, Mo', u'party': u'R', u'total': u'2000'}}, {u'@attributes': {u'cid': u'N00025292', u'pacs': u'2000', u'indivs': u'0', u'state': u'Utah',u'member_name': u'Bishop, Rob', u'party': u'R', u'total': u'2000'}}, {u'@attributes': {u'cid': u'N00032441', u'pacs': u'1000', u'indivs': u'750', u'state':u'Florida', u'member_name': u'Nugent, Richard', u'party': u'R', u'total': u'1750'}}, {u'@attributes': {u'cid': u'N00024866', u'pacs': u'1000', u'indivs':u'500', u'state': u'Guam', u'member_name': u'Bordallo, Madeleine Z', u'party': u'D', u'total': u'1500'}}, {u'@attributes': {u'cid': u'N00006423', u'pacs':u'1000', u'indivs': u'0', u'state': u'Arizona', u'member_name': u'Franks, Trent', u'party': u'R', u'total': u'1000'}}, {u'@attributes': {u'cid': u'N00009759', u'pacs': u'1000', u'indivs': u'0', u'state': u'Washington', u'member_name': u'Larsen, Rick', u'party': u'D', u'total': u'1000'}}]
```