from pyscihub import pyscihub
sh = SciHub()
logging.basicConfig()
logger = logging.getLogger('Sci-Hub')
SCIHUB_BASE_URL = 'http://sci-hub.cc/'
SCHOLARS_BASE_URL = 'https://scholar.google.com/scholar'
sh.setSCIHUB_BASE_URL(SCIHUB_BASE_URL)
sh.setSCHOLARS_BASE_URL(SCHOLARS_BASE_URL)

file = open('/home/user1/PycharmProjects/generalPurpose/evelo/extendedInfo_smal$

allLines  = file.read().splitlines()
for lines in allLines:
    allElements = lines.split('$')
    print allElements[-1]
    pmid = allElements[0]
    print pmid

    result = sh.download(allElements[-1],path=pmid+".pdf")
    if 'err' in result:
        logger.debug('%s', result['err'])
    else:
        logger.debug('Successfully downloaded file with identifier %s')


