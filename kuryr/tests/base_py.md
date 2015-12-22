### base.py
所有的单元测试 case 的基类。

```py
class TestCase(test_cli20.CLITestV20Base):
    """Test case base class for all unit tests."""

    def setUp(self):
        super(TestCase, self).setUp()
        app.config['DEBUG'] = True
        app.config['TESTING'] = True
        self.app = app.test_client()
        self.app.neutron = self.client
```

TestCase 类继承自 neutronclient.tests.unit.test_cli20。

更进一步地，TestKuryrBase 类继承自 TestCase 类，作为 Kuryr 项目中所有测试 case 的基类。。
