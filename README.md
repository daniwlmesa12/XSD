LOCALIDADES
This project is built to provide information of the weather in Madrid in a certain window of time, stored in a XML, validated in a XSD, and with an API that changes information between the app and the database

Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. 

Prerequisites
Before starting you need some background on NodeJS and JavaScript. Check the links bellow.

To install this project you need a working NodeJS environment. Again see the links bellow...

Installing
Open a command line console and clone this project.

```
git clone https://github.com/daniwlmesa12/XSD.git
```

Go to the new created directory

```
cd XSD/XmlRESTfulNodeJSfromJS
```

Go to the api directory

```
cd api
```

Install all dependencies

```
npm install
```

Boot your API

```
node index.js
```

Test the project with a browser

```
open your favourite browser with the file XSD/XmlRESTfulNodeJSfromJS/web/index.html
```

### XML and XSD files 

An example of XML file sent from client to web service to create a new product:

```
<root xmlns:xsd="https://www.w3.org/2001/XMLSchema"
    xmlns:xsi="https://www.w3.org/2001/XMLSchema-instance" id="28079" version="1.0" xsi:noNamespaceSchemaLocation="api\xsd\localidades.xsd">
    <origen>
        <productor>Agencia Estatal de Meteorología - AEMET. Gobierno de España</productor>
        <web>https://www.aemet.es</web>
        <enlace>https://www.aemet.es/es/eltiempo/prediccion/municipios/madrid-id28079</enlace>
        <language>es</language>
        <copyright>© AEMET. Autorizado el uso de la información y su reproducción citando a AEMET como autora de la misma.</copyright>
        <nota_legal>https://www.aemet.es/es/nota_legal</nota_legal>
    </origen>
```

An example of XML file stored in the Server:

```
<dia fecha="2023-01-29">
            <prob_precipitacion periodo="00-24">0</prob_precipitacion>
            <prob_precipitacion periodo="00-12">0</prob_precipitacion>
            <prob_precipitacion periodo="12-24">0</prob_precipitacion>
            <cota_nieve_prov periodo="00-24"/>
            <cota_nieve_prov periodo="00-12"/>
            <cota_nieve_prov periodo="12-24"/>
            <estado_cielo periodo="00-24" descripcion="Nuboso">14</estado_cielo>
            <estado_cielo periodo="00-12" descripcion="Nuboso">14</estado_cielo>
            <estado_cielo periodo="12-24" descripcion="Nuboso">14</estado_cielo>
            <viento periodo="00-24">
                <direccion>NE</direccion>
                <velocidad>20</velocidad>
            </viento>
            <viento periodo="00-12">
                <direccion>NE</direccion>
                <velocidad>20</velocidad>
            </viento>
            <viento periodo="12-24">
                <direccion>NE</direccion>
                <velocidad>20</velocidad>
            </viento>
            <racha_max periodo="00-24">40</racha_max>
            <racha_max periodo="00-12">40</racha_max>
            <racha_max periodo="12-24">40</racha_max>
            <temperatura>
                <maxima>7</maxima>
                <minima>-1</minima>
            </temperatura>
            <sens_termica>
                <maxima>7</maxima>
                <minima>-1</minima>
            </sens_termica>
            <humedad_relativa>
                <maxima>75</maxima>
                <minima>45</minima>
            </humedad_relativa>
            <uv_max>2</uv_max>
        </dia>
```

XSD file in Server:

```
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="products">
        <xs:complexType>
            <xs:sequence>
                <xs:element name="product" type="productType" maxOccurs="unbounded"/>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <xs:complexType name="productType">
        <xs:sequence>
            <xs:element name="name" type="xs:string"/>
            <xs:element name="price" type="xs:decimal"/>
        </xs:sequence>                        
    </xs:complexType>
</xs:schema>
```

* [NodeJS](https://nodejs.org/es/) - Node.js for the execution of JS
* [xmldom](https://github.com/jindw/xmldom) - A JavaScript implementation of W3C DOM for Node.js.
* [xsd-schema-validator](https://www.npmjs.com/package/xsd-schema-validator) - Allows XML validation with an XML Schema.
* [express-xml-bodyparser](https://github.com/remind101/express-xml-bodyparser) - For those rare cases when you have to parse incoming raw xml-body requests. This middleware works with any connect- or express-based nodejs application.
* [AJAX](https://www.w3schools.com/js/js_ajax_intro.asp) - Allows an HTML client to read, update, create and detele data from a web service.

Authors
Tiburcio Cruz - Initial work
Daniel Mesa - Added the XML and XSD files

License
This project is licensed under the MIT License - see the LICENSE.md file for details

Acknowledgments
Hat tip to anyone whose code was used
Inspiration
etc
