
# README - Python y XML

Proporciona una breu documentació d'XML en Python mitjançant 'xml.dom.minidom'. On hi ha diversos exemples de codi.

## Introducció a Python i XML

Python ofereix moltes biblioteques per treballar amb XML, una de les més comuns 'xml.dom.minidom', on podem analitzar, manipular i generar documents XML d'una forma simple i efectiva.

from xml.dom import minidom

# **Crear el fitxer HTML**
f = open("personal.html", 'w')
f.write('<html><head><title>Personal DOM</title></head>\n')
f.write('<body>\n')

# *Llegir el fitxer XML*
doc = minidom.parse("personal.xml")
tag_example = doc.documentElement
tag_people = tag_example.getElementsByTagName('people')[0]
llista_tag_person = tag_people.getElementsByTagName('person')

# Recórrer cada persona i escriure la informació en HTML
for tag_person in llista_tag_person:
    id = tag_person.getAttribute('id')
    tag_name = tag_person.getElementsByTagName('name')[0]
    name = tag_name.firstChild.data
    gender = tag_name.getAttribute('gender')
    age = tag_person.getElementsByTagName('age')[0].firstChild.data
    naixement = tag_person.getElementsByTagName('naixement')[0].firstChild.data

    f.write(f'<h2>{id} - {name}</h2>\n')
    f.write('<ul>\n')
    f.write(f'<li>edat - {age}</li>\n')
    f.write(f'<li>sexe - {gender}</li>\n')
    f.write(f'<li>naixement - {naixement}</li>\n')
    f.write('</ul>\n')

f.write('</body></html>')
f.close()


### Exemples:

- Enllaços: [Documentació xml.dom.minidom](https://docs.python.org/3/library/xml.dom.minidom.html#dom-example)
- Imatges: (https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.linkedin.com%2Fpulse%2Fintroduction-data-transformation-python-using-xslt-tejas-bhandari&psig=AOvVaw2DtLYcTw3WCACycxdiMnEI&ust=1712338365108000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCOCikdKLqYUDFQAAAAAdAAAAABAE)

Aquí el bloc de codi convertit en un llistat d'elements:

- **id - name**
  - edat - age
  - sexe - gender
  - naixement - naixement



