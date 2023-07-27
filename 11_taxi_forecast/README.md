#  ��������������� ������� �����

**�����������**

Python, 
Pandas, 
Scikit-learn, 
statsmodels

�������� �׸������� ����� ������� ������������ ������ � ������� ����� � ����������. ����� ���������� ������ ��������� � ������ ������� ��������, ����� ��������������� ���������� ������� ����� �� ��������� ���. 

��������: �������� ������� *RMSE* �� �������� ������� ������ ���� �� ������ 48.

��� �����:

1. ��������� ������ � ��������� �� ��������������� �� ������ ����.
2. ���������������� ������.
3. ������� ������ ������ � ���������� ����������������. ������� �������� ������� �������� 10% �� �������� ������.
4. ��������� ������ �� �������� ������� � ������� ������.


������ ����� � ����� `taxi.csv`. ���������� ������� ��������� � ������� `num_orders`.


<h1>����������<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#����������" data-toc-modified-id="����������-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>����������</a></span></li><li><span><a href="#������" data-toc-modified-id="������-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>������</a></span></li><li><span><a href="#��������" data-toc-modified-id="��������-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>��������</a></span><ul class="toc-item"><li><span><a href="#��������-���������" data-toc-modified-id="��������-���������-3.1"><span class="toc-item-num">3.1&nbsp;&nbsp;</span>�������� ���������</a></span></li><li><span><a href="#�����������-������" data-toc-modified-id="�����������-������-3.2"><span class="toc-item-num">3.2&nbsp;&nbsp;</span>����������� ������</a></span></li><li><span><a href="#GradientBoostingRegressor" data-toc-modified-id="GradientBoostingRegressor-3.3"><span class="toc-item-num">3.3&nbsp;&nbsp;</span>GradientBoostingRegressor</a></span></li><li><span><a href="#���������-���" data-toc-modified-id="���������-���-3.4"><span class="toc-item-num">3.4&nbsp;&nbsp;</span>��������� ���</a></span></li><li><span><a href="#��������-�����" data-toc-modified-id="��������-�����-3.5"><span class="toc-item-num">3.5&nbsp;&nbsp;</span>�������� �����</a></span></li></ul></li><li><span><a href="#������������" data-toc-modified-id="������������-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>������������</a></span></li><li><span><a href="#���-����-��������" data-toc-modified-id="���-����-��������-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>���-���� ��������</a></span></li></ul></div>

��������� ��������� ��� �������� ������ �� �������� ������ ������� ����������� ������� 23.46, �������� ������ �� �������� �������. �������� ������� RMSE �� �������� ������� 37.20, ��� ������������� �������� ������.