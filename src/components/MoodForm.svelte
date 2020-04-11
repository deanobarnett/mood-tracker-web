<style>
  textarea.form-control {
    height: 15em;
  }
</style>

<svelte:head>
  <title>Mood Tracker</title>
</svelte:head>

<script>
    import { Button, Container, Form, FormGroup, Label, Input, Row, Col } from 'sveltestrap/src';
</script>

<Container>
  <Form>
    <FormGroup>
      <Row>
        <Col>
          <Input
            type="number"
            name="sleep"
            id="sleep"
            placeholder="sleep" />
        </Col>
        <Col>
          <Input
            type="number"
            name="mood"
            id="mood"
            placeholder="mood" />
        </Col>
        <Col>
          <Input
            type="number"
            name="stress"
            id="stress"
            placeholder="stress" />
        </Col>
      </Row>
    </FormGroup>
    <FormGroup>
      <Row>
        <Col>
          <Input type="textarea" name="notes" id="notes" />
        </Col>
      </Row>
    </FormGroup>
    <Button color="primary">
      Submit
    </Button>
  </Form>
</Container>
