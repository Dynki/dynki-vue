<script>
import { Form } from "ant-design-vue";
import { Component, Vue } from "vue-property-decorator";

const NormalLoginForm = {
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      this.form.validateFields((err, values) => {
        if (!err) {
          console.log("Received values of form: ", values);
        }
      });
    }
  },

  render() {
    const { getFieldDecorator } = this.form;
    return (
      <a-form
        id="components-form-demo-normal-login"
        onSubmit={this.handleSubmit}
        class="login"
      >
        <h1 class="login__heading">Welcome</h1>
        <a-form-item>
          {getFieldDecorator("userName", {
            rules: [{ required: true, message: "Please input your username!" }]
          })(
            <a-input
              size="large"
              prefix={
                <a-icon type="user" style={{ color: "rgba(0,0,0,.25)" }} />
              }
              placeholder="Username"
            />
          )}
        </a-form-item>
        <a-form-item>
          {getFieldDecorator("password", {
            rules: [{ required: true, message: "Please input your Password!" }]
          })(
            <a-input
              size="large"
              prefix={
                <a-icon type="lock" style={{ color: "rgba(0,0,0,.25)" }} />
              }
              type="password"
              placeholder="Password"
            />
          )}
        </a-form-item>
        <a-form-item>
          {getFieldDecorator("remember", {
            valuePropName: "checked",
            initialValue: true
          })(<a-checkbox>Remember me</a-checkbox>)}
          <a class="login-form-forgot" href="">
            Forgot password
          </a>
          <a-button type="dashed" htmlType="submit" class="domain__btn">
            Sign in
            <a-icon type="enter"/>
          </a-button>
          Or <a href="">register now!</a>
        </a-form-item>
      </a-form>
    );
  }
};

export default Form.create()(NormalLoginForm);
</script>
