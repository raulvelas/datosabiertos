# Perfil Regional de Metadatos

<table class="docutils">
<thead>
<tr><th>Nombre                                     </th><th>Requerido  </th><th>Descripción                                                                                                                                                                                                                                                </th><th>Ejemplo                                                        </th><th>Variable             </th><th>Tipo           </th></tr>
</thead>
<tbody>
<tr><td>Identificador                              </td><td>R          </td><td>Es el identificador único del catálogo dentro de la red de catálogos de datos abiertos a la que pertenece. Este identificador puede ser otorgado por el área a cargo de la política de apertura de un país a sus organismos, o establecido por alguna convención internacional para el caso de catálogos de jerarquía jurisdiccional nacional.

El identificador debe ser una o más palabras en minúsculas, separadas con guiones medios, sin usar caracteres especiales. Identifica en forma breve, sucinta y declarativa al catálogo.                                                                                                                                                                                                                                                            </td><td>"energia"

"desarrollo-social"

"justicia"

"argentina"

"mexico"                                                                </td><td>identifier           </td><td>String         </td></tr>
<tr><td>Título                                     </td><td>Si         </td><td>Nombre dado al catálogo. Debe ser claro, breve y lo suficientemente abstracto como para abarcar la multiplicidad de datasets que contiene.                                                                                                                 </td><td>Datos Argentina                                                </td><td>title                </td><td>String         </td></tr>
<tr><td>Descripción                                </td><td>Si         </td><td>Descripción del contenido del catálogo.                                                                                                                                                                                                                    </td><td>Portal de Datos Abiertos del Gobierno de la República Argentina</td><td>description          </td><td>String         </td></tr>
<tr><td>Autor                                      </td><td>Si         </td><td>Autoridad responsable de la publicación del catálogo.                                                                                                                                                                                                      </td><td>Ministerio de Modernización                                    </td><td>publisher -&gt; name    </td><td>String         </td></tr>
<tr><td>Correo electrónico del autor               </td><td>Si         </td><td>Correo electrónico de contacto de la autoridad responsable de la publicación del catálogo.                                                                                                                                                                 </td><td>datos@modernizacion.gob.ar                                     </td><td>publisher -&gt; mbox    </td><td>String         </td></tr>
<tr><td>Datasets                                   </td><td>Si         </td><td>Contiene una lista de los datasets que forman parte del catálogo.                                                                                                                                                                                          </td><td>[{...}, {...}]                                                 </td><td>dataset              </td><td>Array          </td></tr>
<tr><td>Fecha de creación o publicación            </td><td>R          </td><td>Fecha de creación o publicación del catálogo. Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                            </td><td>"2016-04-14T19:48:05.433640" para especificar fecha y hora

"2016-04-14" para especificar fecha únicamente                                                                </td><td>issued               </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>R          </td><td>Fecha de última actualización/modificación del catálogo (ya sea de sus datos o de sus metadatos). Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.        </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>modified             </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>No         </td><td>Fecha de última actualización/modificación de los datos del catálogo. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el catálogo.                                              </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>dataModified         </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>No         </td><td>Fecha de última actualización/modificación de los metadatos del catálogo. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el catálogo.                                          </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>metadataModified     </td><td>String         </td></tr>
<tr><td>Idioma(s)                                  </td><td>R          </td><td>Lenguaje para la descripción de los metadatos de los datasets contenidos en el catálogo. Hay 2 estándares ISO que pueden ser utilizados para este campo:

(a) ISO 639-1 (2 letras)
(b) ISO 639-2/T (3 letras) es el más recomendado.

Puede definirse 1 o más lenguajes en una lista. (Link a los estándares ISO: https://www.loc.gov/standards/iso639-2/php/code_list.php)                                                                                                                                                                                                                                                            </td><td>["es"] para un lenguaje ISO 639-1

["spa", ”eng"] para dos lenguajes ISO 639-2                                                                </td><td>language             </td><td>Array          </td></tr>
<tr><td>Taxonomía temática                         </td><td>R          </td><td>Es el sistema de clasificación temática, creado por la organización responsable del catálogo.

Compone una lista de temas que se pueden usar para clasificar los datasets del catálogo. Si se clasifica a algún dataset del catálogo como perteneciente a uno o más temas, este campo es obligatorio ya que se debe explicitar una taxonomía temática para poder usar sus temas.

Para catálogos nacionales o que reúnen datasets de temáticas variadas, se recomienda utilizar la taxonomía temática de la Unión Europea (Ver standards/themeTaxonomy).                                                                                                                                                                                                                                                            </td><td>[{...}, {...}]                                                 </td><td>themeTaxonomy        </td><td>Array          </td></tr>
<tr><td>Licencia                                   </td><td>R          </td><td>Indica la licencia bajo la cual todos los datasets y distribuciones del catálogo están disponibles mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de http://opendefinition.org/licenses/.

Se recomienda utilizar la licencia "Open Database License (ODbL) v1.0". Un dataset o distribución que especifique una licencia diferente, sobreescribe a la licencia general del catálogo.                                                                                                                                                                                                                                                            </td><td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace

"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar                                                                </td><td>license              </td><td>String         </td></tr>
<tr><td>Página web del catálogo                    </td><td>R          </td><td>Dirección web o enlace de acceso a la página principal del catálogo                                                                                                                                                                                        </td><td>http://datos.gob.ar                                            </td><td>homepage             </td><td>String         </td></tr>
<tr><td>Derechos sobre el catálogo                 </td><td>No         </td><td>Información sobre derechos aplicables al catálogo en el caso que no se hayan especificado en la licencia. Los datasets y sus distribuciones heredan la información sobre derechos aplicables al catálogo, a menos que especifiquen unos derechos distintos.</td><td>nan                                                            </td><td>rights               </td><td>String         </td></tr>
<tr><td>Cobertura geográfica                       </td><td>No         </td><td>El área geográfica cubierta por el catálogo.

Una región o un lugar determinado. Puede tomar valores:

a) de países y, provincias y municipios argentinos, según las recomendaciones de la “Guía para la identificación y uso de entidades interoperables”.
b) un área de coordenadas representada por latitud/ longitud en el orden: minima longitud, minima latitud, maxima longitud, maxima latitud.
c) un punto geográfico representado por latitud/longitud.
d) Si la referencia geográfico no está identificada en la “Guía para la identificación y uso de entidades interoperables” indicar la URIs según geonames.org; ej :
http://sws.geonames.org/6255146                                                                                                                                                                                                                                                            </td><td>"ARG" es el código para la República Argentina.

"06007" es el código de un departamento

[-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box

[-58.111111, -35.111111] es un punto geográfico

"http://sws.geonames.org/6255146"                                                                </td><td>spatial              </td><td>String or Array</td></tr>
<tr><td>Version del perfil de metadatos            </td><td>R          </td><td>Es la versión del perfil de metadatos utilizada en el catálogo.

Se utiliza para que distintas aplicaciones reconozcan y validen los metadatos del catálogo, y las funcionalidades disponibles para distintos fines.                                                                                                                                                                                                                                                            </td><td>1.0                                                            </td><td>metadataSchemeVersion</td><td>String         </td></tr>
</tbody>
</table>