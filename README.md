# alexa telleng us the temperature of the water / capacity of our solar storage

```
<xml xmlns="https://developers.google.com/blockly/xml">
  <variables>
    <variable id="W|v+f/xO((5nlL|.UoUX">txt</variable>
  </variables>
  <block type="on_ext" id="l3u_cJZVO=D!E:8cI*SC" x="63" y="13">
    <mutation xmlns="http://www.w3.org/1999/xhtml" items="1"></mutation>
    <field name="CONDITION">ne</field>
    <field name="ACK_CONDITION"></field>
    <value name="OID0">
      <shadow type="field_oid" id="K%o09$D|xauyapG7oea0">
        <field name="oid">alexa2.0.History.summary</field>
      </shadow>
    </value>
    <statement name="STATEMENT">
      <block type="controls_if" id="F^O%L}B]*Uf*Y,X|E:0(">
        <value name="IF0">
          <block type="logic_compare" id="~]_NNjW,+,aMrOzEz:S6">
            <field name="OP">GT</field>
            <value name="A">
              <block type="text_indexOf" id="HiXs|bgl7Ex;PLDrd!R`">
                <field name="END">FIRST</field>
                <value name="VALUE">
                  <block type="on_source" id="`L)_oRF7xz@rmo3zJLbZ">
                    <field name="ATTR">state.val</field>
                  </block>
                </value>
                <value name="FIND">
                  <shadow type="text" id="8:q#e/+oIQ5Db.kfXPe@">
                    <field name="TEXT">ist das wasser</field>
                  </shadow>
                </value>
              </block>
            </value>
            <value name="B">
              <block type="math_number" id=")}QfeKV!-tZwA)Pje%hD">
                <field name="NUM">0</field>
              </block>
            </value>
          </block>
        </value>
        <statement name="DO0">
          <block type="variables_set" id=",4mCs7YNTEGJkt^?w}a@">
            <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
            <value name="VALUE">
              <block type="text_join" id="6eU_N2Ms4$./G){$C!Jq">
                <mutation items="2"></mutation>
                <value name="ADD0">
                  <block type="text_join" id="UzH#%0*-aI*+aMFzF(kM">
                    <mutation items="2"></mutation>
                    <value name="ADD0">
                      <block type="text" id="[V^NkQ[q:?.mU*VI8CV{">
                        <field name="TEXT">Die Wassertermperatur beträgt </field>
                      </block>
                    </value>
                    <value name="ADD1">
                      <block type="get_value" id="^^a|yX4e#2w[lO?w6]F*">
                        <field name="ATTR">val</field>
                        <field name="OID">mqtt.0.wasser.temperatur</field>
                      </block>
                    </value>
                  </block>
                </value>
                <value name="ADD1">
                  <block type="text" id=");_3X@?y*Q%+U)49=vLU">
                    <field name="TEXT">Grad</field>
                  </block>
                </value>
              </block>
            </value>
            <next>
              <block type="comment" id="tGx_o1A+-Vv!Bpb2=or.">
                <field name="COMMENT">TV</field>
                <next>
                  <block type="control" id="IvEQXR@FFr!j`$f30}Jl">
                    <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="true"></mutation>
                    <field name="OID">alexa2.0.Echo-Devices.G070L81693751XAQ.Commands.speak</field>
                    <field name="WITH_DELAY">TRUE</field>
                    <field name="DELAY_MS">100</field>
                    <field name="UNIT">ms</field>
                    <field name="CLEAR_RUNNING">FALSE</field>
                    <value name="VALUE">
                      <block type="variables_get" id="h$?e^j;Rcyb.;6{;;RoT">
                        <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                      </block>
                    </value>
                    <next>
                      <block type="comment" id="qAA`F[uP8JaH5Wkg$/_T">
                        <field name="COMMENT">Bad</field>
                        <next>
                          <block type="control" id="MP,?-F#VD1,LHeI7@m-/">
                            <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="false"></mutation>
                            <field name="OID">alexa2.0.Echo-Devices.8c4e0129d54b472c94d4ad76e4f9a9c6.Commands.speak</field>
                            <field name="WITH_DELAY">FALSE</field>
                            <value name="VALUE">
                              <block type="variables_get" id="1aPI@PUb;!:._9#f63=z">
                                <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                              </block>
                            </value>
                            <next>
                              <block type="comment" id="X4(4o02+y7r$+t$f}]YE">
                                <field name="COMMENT">Bett</field>
                                <next>
                                  <block type="control" id="mH.S{U_Z3+@n3`i8@jz8">
                                    <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="false"></mutation>
                                    <field name="OID">alexa2.0.Echo-Devices.G090LF1181753U3V.Commands.speak</field>
                                    <field name="WITH_DELAY">FALSE</field>
                                    <value name="VALUE">
                                      <block type="variables_get" id="%@*GoLWwGE#O#tPTc63t">
                                        <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                                      </block>
                                    </value>
                                  </block>
                                </next>
                              </block>
                            </next>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </statement>
        <next>
          <block type="controls_if" id="BQFx*GYC[8E@Px4Ysy1|">
            <value name="IF0">
              <block type="logic_compare" id="@QZ,M3W[)bREJCT8kHEK">
                <field name="OP">GT</field>
                <value name="A">
                  <block type="text_indexOf" id="1#])C1{BKC+zqFvWy*0-">
                    <field name="END">FIRST</field>
                    <value name="VALUE">
                      <block type="on_source" id="EeR)s*H3z^fo+*Eb.uL~">
                        <field name="ATTR">state.val</field>
                      </block>
                    </value>
                    <value name="FIND">
                      <shadow type="text" id="(d!Zt}*0pOaSiBitq#xy">
                        <field name="TEXT">fit ist der akku</field>
                      </shadow>
                    </value>
                  </block>
                </value>
                <value name="B">
                  <block type="math_number" id="itm2,[e*:zb3)VL]Ad?p">
                    <field name="NUM">0</field>
                  </block>
                </value>
              </block>
            </value>
            <statement name="DO0">
              <block type="variables_set" id="9hDVj1BS5g::f|Vl2Fv^">
                <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                <value name="VALUE">
                  <block type="text_join" id="$X=c+_.!+X.x]Pny{hh;">
                    <mutation items="2"></mutation>
                    <value name="ADD0">
                      <block type="text_join" id="AD-aF~*HzWz%Z++oXq.6">
                        <mutation items="2"></mutation>
                        <value name="ADD0">
                          <block type="text" id="QG7Wv#0[+2#dm}B$Ah[j">
                            <field name="TEXT">Der Akku ist zu </field>
                          </block>
                        </value>
                        <value name="ADD1">
                          <block type="get_value" id="nikDJrkZYhjh:oGjEl6{">
                            <field name="ATTR">val</field>
                            <field name="OID">mqtt.0.pythonrct.akkustatus</field>
                          </block>
                        </value>
                      </block>
                    </value>
                    <value name="ADD1">
                      <block type="text" id="J/?-C#o#1ac(q7}{}n[m">
                        <field name="TEXT">Prozent geladen</field>
                      </block>
                    </value>
                  </block>
                </value>
                <next>
                  <block type="comment" id="*R5}NNjI?qLT^3[9YJ_F">
                    <field name="COMMENT">TV</field>
                    <next>
                      <block type="control" id="Ue3Oj]|}y+cP0+gRCU]*">
                        <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="true"></mutation>
                        <field name="OID">alexa2.0.Echo-Devices.G070L81693751XAQ.Commands.speak</field>
                        <field name="WITH_DELAY">TRUE</field>
                        <field name="DELAY_MS">100</field>
                        <field name="UNIT">ms</field>
                        <field name="CLEAR_RUNNING">FALSE</field>
                        <value name="VALUE">
                          <block type="variables_get" id="y8g^e9zz}X7bNRD`Pl{)">
                            <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                          </block>
                        </value>
                        <next>
                          <block type="comment" id="^v~n=m-PbA,:6gBmj11$">
                            <field name="COMMENT">Bad</field>
                            <next>
                              <block type="control" id="uq(Zt}l|P^WqUi=D^odE">
                                <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="false"></mutation>
                                <field name="OID">alexa2.0.Echo-Devices.8c4e0129d54b472c94d4ad76e4f9a9c6.Commands.speak</field>
                                <field name="WITH_DELAY">FALSE</field>
                                <value name="VALUE">
                                  <block type="variables_get" id="ew^%BL*yiATPxR;E||lz">
                                    <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                                  </block>
                                </value>
                                <next>
                                  <block type="comment" id="MQXqR@v]MyR4TB^@hZO0">
                                    <field name="COMMENT">Bett</field>
                                    <next>
                                      <block type="control" id="qFTNfpdnu:DxlRNTL6J(">
                                        <mutation xmlns="http://www.w3.org/1999/xhtml" delay_input="false"></mutation>
                                        <field name="OID">alexa2.0.Echo-Devices.G090LF1181753U3V.Commands.speak</field>
                                        <field name="WITH_DELAY">FALSE</field>
                                        <value name="VALUE">
                                          <block type="variables_get" id="ELHh~~4XZHs{DAv$.r3V">
                                            <field name="VAR" id="W|v+f/xO((5nlL|.UoUX">txt</field>
                                          </block>
                                        </value>
                                      </block>
                                    </next>
                                  </block>
                                </next>
                              </block>
                            </next>
                          </block>
                        </next>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </statement>
          </block>
        </next>
      </block>
    </statement>
  </block>
</xml>
´´´
