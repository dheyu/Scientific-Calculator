Public Class Form1
    Dim f As Double
    Dim s As Double
    Dim a As Double
    Dim op As String
    Dim n As Int32


    Private Sub Button_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button9.Click, Button8.Click, Button7.Click, Button3.Click, Button22.Click, Button2.Click, Button19.Click, Button15.Click, Button14.Click, Button13.Click
        Dim b As Button = sender
        If Label1.Text = "0" Then
            Label1.Text = b.Text
        Else
            Label1.Text = Label1.Text + b.Text

        End If
    End Sub

    Private Sub Button21_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button21.Click
        Label1.Text = "0"
        Label3.Text = "0"
    End Sub

    Private Sub Button25_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button25.Click
        Label1.Text = "0"
        Label3.Text = "0"
    End Sub

    Private Sub arithmatic_function(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button4.Click, Button5.Click, Button23.Click, Button20.Click, Button16.Click, Button12.Click
        Dim ops As Button = sender
        f = Label1.Text
        Label3.Text = Label1.Text
        Label1.Text = ""
        op = ops.Text
        Label3.Text = Label3.Text + " " + op

    End Sub

    Private Sub Button26_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button26.Click
        s = Label1.Text
        If op = "+" Then
            a = f + s
            Label1.Text = a
            Label3.Text = ""
        ElseIf op = "-" Then
            a = f - s
            Label1.Text = a
            Label3.Text = ""
        ElseIf op = "*" Then
            a = f * s
            Label1.Text = a
            Label3.Text = ""
        ElseIf op = "/" Then
            a = f / s
            Label1.Text = a
            Label3.Text = ""
        ElseIf op = "Mod" Then
            a = f Mod s
            Label1.Text = a
            Label3.Text = ""
        ElseIf op = "Exp" Then
            a = f ^ s
            Label1.Text = a
            Label3.Text = ""
        End If
    End Sub

    Private Sub Button11_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button11.Click
        If Int32.TryParse(Label1.Text, n) Then
            Label1.Text = Convert.ToString(n, 2)
        Else
            Label1.Text = ""

        End If
    End Sub

    Private Sub Button6_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button6.Click
        a = Math.Sin(Label1.Text)
        Label1.Text = a
        Label3.Text = ""
    End Sub

    Private Sub Button10_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button10.Click
        a = Math.Cos(Label1.Text)
        Label1.Text = a
        Label3.Text = ""
    End Sub

    Private Sub Button17_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button17.Click
        a = Math.Tan(Label1.Text)
        Label1.Text = a
        Label3.Text = ""
    End Sub

    Private Sub Button18_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button18.Click
        a = Math.Log(Label1.Text)
        Label1.Text = a
        Label3.Text = ""
    End Sub

    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load
        Me.Height = 423
        Me.Width = 269
        Button26.Width = 112
        Label1.Width = 229

        ComboBox1.Text = "Choose One..."
        ComboBox1.Items.Add("Celsius to Fahrenheit")
        ComboBox1.Items.Add("Fahrenheit to Celsius")
        ComboBox1.Items.Add("Miles to Kilometres")
        ComboBox1.Items.Add("Kilometres to miles")
        ComboBox1.Items.Add("Centimetre to Metres")
    End Sub

    Private Sub Button28_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button28.Click
        Dim convt As Double
        If ComboBox1.Text = "Celsius to Fahrenheit" Then
            convt = (9 / 5 * TextBox2.Text) + 32
            Label2.Text = (convt) & "Fahrenheit"
        ElseIf ComboBox1.Text = "Fahrenheit to Celsius" Then
            convt = (5 / 9 * TextBox2.Text) - 32
            Label2.Text = (convt) & "Celcius"
        ElseIf ComboBox1.Text = "Miles to Kilometres" Then
            convt = (TextBox2.Text * 1.609344)
            Label2.Text = (convt) & "Kilometres"
        ElseIf ComboBox1.Text = "Kilometres to miles" Then
            convt = (TextBox2.Text / 1.609344)
            Label2.Text = (convt) & "miles"
        ElseIf ComboBox1.Text = "Choose One..." Or TextBox2.Text = "" Then
            MsgBox("Select the Unit of Conversion", "Calculator Plus", vbInformation)
        End If
    End Sub

    Private Sub ScientificToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles ScientificToolStripMenuItem.Click
        Me.Height = 423
        Me.Width = 393
        Button26.Width = 238
        Label1.Width = 355
    End Sub

    Private Sub UnitConversionToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles UnitConversionToolStripMenuItem.Click
        Me.Height = 423
        Me.Width = 657
        Button26.Width = 238
        Label1.Width = 355
    End Sub

    Private Sub StandardToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles StandardToolStripMenuItem.Click
        Me.Height = 423
        Me.Width = 269
        Button26.Width = 112
        Label1.Width = 229
    End Sub

    Private Sub ExitToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles ExitToolStripMenuItem.Click
        Application.Exit()
    End Sub

    Private Sub Button27_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button27.Click
        Label2.Text = ""
        TextBox2.Text = ""
    End Sub
End Class

